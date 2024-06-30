
**Interfaces**
- define the **relationship** between components
- define the **structure** and **behavior** of the system
- connection to the outside world

Interfaces must fulfill user (mostly consumer) requirements
- suitable functionality (difficult for public APIs)
- Easy to learn and use
	- Provide **IDL** (e.g. Swagger)
	- Use unit tests as documentation
- Easy to extend
	- Consider API versioning
- Hard to misuse (intentional and unintentional)
- Consistent to other interfaces in the system


### Best Practices
- use it yourself, implement tests and use the tests as a reference example
- clarify requirements with the customer and provider
- hide implementation details (information hiding principle)
- use meaningful, self-descriptive names
- minimize surprises and side effects (**principle of least surprise**)
- provide **atomic** information units
- documentation (especially for boundary/threshold example and errors)

### Java Message Services (JMS)

**Key Concepts:**
- Point-to-Point (P2P) messaging (Queue | One-to-many messaging)
- Storage | delivery | routing through message brokers
- Message types: text, bytes, objects, maps, streams


```java
public class JMSProducer {

      private static final String BROKER_URL = "tcp://localhost:61616";

      private static final String QUEUE_NAME = "dynamicQueues/myqueue";

      public static void main(String[] args) throws Exception {

            MessageService jms = new MessageService();

            Session session = jms.start(BROKER_URL, QUEUE_NAME);

            MessageProducer producer = jms.createProducer();

            System.out.println("Enter a new message / enter an empty line to close provider session");

            Scanner keyboard = new Scanner(System.in);

            String line;

            while(!(line = keyboard.nextLine()).isBlank()) {

                  Message msg = session.createTextMessage(line);

                  producer.send(msg);
            }

            keyboard.close();

            System.out.println("Shutting down Producer");

            jms.stop();
      }
}


public class JMSConsumer {

      private static final String BROKER_URL = "tcp://localhost:61616";

      private static final String QUEUE_NAME = "dynamicQueues/myqueue";

      public static record ConsumerMessageListener(String consumerName) implements MessageListener {

            public void onMessage(Message message) {

                  TextMessage textMessage = (TextMessage) message;

                  try {

                        System.out.println(consumerName + " received: '" + textMessage.getText() + "'");

                  } catch (JMSException e) {

                        e.printStackTrace();
                  }
            }
      }

      public static void main(String[] args) throws Exception {        

            MessageService jms = new MessageService();

            jms.start(BROKER_URL, QUEUE_NAME);

        MessageConsumer consumer = jms.createConsumer();

        consumer.setMessageListener(new ConsumerMessageListener("Consumer"));

            System.out.println("Press 'Enter' to close consumer session");

            Scanner keyboard = new Scanner(System.in);

            keyboard.nextLine();

            keyboard.close();

            System.out.println("Shutting down Consumer");

            jms.stop();
      }
}


public class MessageService {

      private boolean running = false;

      private BrokerService broker;

      private Connection connection;

      private Queue queue;

      private Session session;

      private BrokerService createBroker(String brokerUrl) {

            BrokerService broker = null;

            try {

                  broker = BrokerFactory.createBroker(new URI("broker:(" + brokerUrl + ")"));

            } catch (URISyntaxException e) {

                  e.printStackTrace();

                  System.exit(0);

            } catch (Exception e) {

//                e.printStackTrace();

                  System.err.println("Broker already running");
            }
            return broker;
      }

      private InitialContext createInitalContext(String brokerUrl) {

            try {

                  Properties props = new Properties();

                  props.setProperty(Context.INITIAL_CONTEXT_FACTORY, "org.apache.activemq.jndi.ActiveMQInitialContextFactory");

                  props.setProperty(Context.PROVIDER_URL, brokerUrl);

                  InitialContext context = new InitialContext(props);

                  return context;

            } catch (NamingException e) {

                  e.printStackTrace();

                  System.exit(0);
            }
            return null;
      }

      private Connection createQueueConnection(InitialContext context) {

            try {

                  QueueConnectionFactory connFactory = (QueueConnectionFactory)context.lookup("ConnectionFactory");        

                  Connection connection = connFactory.createQueueConnection();

                  connection.start();

                  return connection;

            } catch (NamingException | JMSException e) {

                  e.printStackTrace();

                  System.exit(0);

            }
            return null;
      }

      public Session start(String brokerUrl, String queueName) {

            try {
                  broker = createBroker(brokerUrl);

                  if(broker != null) broker.start();        

                  InitialContext ctx = createInitalContext(brokerUrl);

                  connection = createQueueConnection(ctx);

                  queue = (Queue) ctx.lookup(queueName);          

                  session = connection.createSession(false, Session.AUTO_ACKNOWLEDGE);

                  running = true;

                  return session;

            } catch (Exception e) {

                  e.printStackTrace();

                  return null;
            }
      }
  

      public MessageConsumer createConsumer() {

            try {

                  if(running) return session.createConsumer(queue);

            } catch (JMSException e) {
                  e.printStackTrace();
            }

            return null;
      }

  

      public MessageProducer createProducer() {

            try {

                  if(running) return session.createProducer(queue);

            } catch (JMSException e) {
                  e.printStackTrace();
            }

            return null;

      }

      public void stop() {

            try {

                  session.close();

                  connection.close();

                  if(broker != null) broker.stop();

                  session = null;

                  connection = null;

                  broker = null;

                  queue = null;

                  running = false;

            } catch (Exception e) {
                  e.printStackTrace();
            }
      }
}
```

### Representational State Transfer (REST)
- Business objects are referenced as Web resources
- Variours

### Simple Object Access Protocol (SOAP)


