🐍 Customized Logging in Python

A quick guide to setting up custom loggers in Python using the logging module.

Why Customize?

Root logger is basic and shared — not ideal for large apps.

Custom loggers give better control over formatting, levels, and output.

🔧 Steps to Create a Custom Logger
1. Create a Logger

logger = logging.getLogger('demologger')
logger.setLevel(logging.INFO)

2. Create Handlers

consoleHandler = logging.StreamHandler()
fileHandler = logging.FileHandler('test.log')

3. Set Handler Levels

consoleHandler.setLevel(logging.INFO)
fileHandler.setLevel(logging.INFO)

4. Create and Set Formatter

formatter = logging.Formatter(
    '%(asctime)s - %(name)s - %(levelname)s: %(message)s',
    datefmt='%d/%m/%Y %I:%M:%S %p'
)
consoleHandler.setFormatter(formatter)
fileHandler.setFormatter(formatter)

5. Add Handlers to Logger

logger.addHandler(consoleHandler)
logger.addHandler(fileHandler)

6. Log Messages

logger.debug('debug message')
logger.info('info message')
logger.warning('warn message')
logger.error('error message')
logger.critical('critical message')
