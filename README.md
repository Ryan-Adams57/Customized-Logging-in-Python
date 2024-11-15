# Customized-Logging-in-Python

In this repository, I am going to showcase Customized Logging in Python with examples.

Root Logger in Python Logging Module, Problems with root logger. Customized Logging in Python, and Steps for creating a custom logger.

Step 1: Create a logger

First we need to create a logger, which is nothing but an object to the logger class. We can create this by using getLogger() method. After creating the logger object we have to set the log level using setLevel() method.

logger = logging.getLogger(‘demologger’)
logger.setLevel(logging.INFO)

We can give any name to the logger as we wish. In the above example, a logger with name ‘demologger’ will be created.

Step 2: Creating handler

The next step is to create a handler object and set the logging level. There are several types of Handlers like StreamHandler, FileHandler etc. If we use StreamHandler then log messages will be printed to the console. If we use FileHandler, then the log messages will be printed into file.

For Stream Handler,
consoleHandler = logging.StreamHandler()
consoleHandler.setLevel(logging.INFO)

For File Handler,
fileHandler = logging.FileHandler(‘test.log’)
fileHandler.setLevel(logging.INFO)

Step 3: Creating Formatter

The next step is to create a formatter object.

formatter = logging.Formatter(‘%(asctime)s – %(name)s – %(levelname)s:
%(message)s’, datefmt=’%d/%m/%Y %I:%M:%S %p’)

Step 4: Adding Formatter to Handler

Now we have to add the Formatter (object) to Handler (object) using setFormatter() method.

consoleHandler.setFormatter(formatter)

Step 5: Adding Handler object to the Logger

Then the handler object should be added to the logger object using addHandler() method.

logger.addHandler(fileHandler)
logger.addHandler(streamHandler)

Step 6: Writing the log messages

The last step is writing the log messages to the file using the methods and logger object which we created.

logger.debug(‘debug message’)
logger.info(‘info message’)
logger.warn(‘warn message’)
logger.error(‘error message’)
logger.critical(‘critical message’)
