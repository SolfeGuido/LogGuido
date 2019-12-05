# LogGuido

A threaded rolling logger for löve2D.

Used by [SolfeGuido](https://github.com/SolfeGuido/SolfeGuido)

Usage :

```lua
-- Start the thread
Logger.init(config)

-- Log a simple message
Logger.log('INFO', 'message')
-- or
Logger.info('message')

-- Warning, error, fatal
Logger.warning(warningMessage)
Logger.error(errorMessage)
Logger.fatal(fatalMessage)

-- Try to execute an action, log if it fails
local result = Logger.try('To get a value', function() return getAValue() end, 'defaultValue')

-- Close the thread
Logger.close()
```

## Configuration

The configuration given at the init function can contains the following values :

_logFile_ : Name of the file where to write the logs (default = logs.log)

_maxSize_ : Max size of the file where the logs are written, once this size is reached, the logger creates a new zip file with the content of the logFile and deletes the logFile (default = 5MB)

_logZip_ : Name of the zip file to create once the logFile is too big. (default = <_logFile_>.zip)

This logger only creates one zip, if the zip file already exists, it will just delete it
