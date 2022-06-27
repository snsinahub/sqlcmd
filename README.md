# sqlcmd

snsinahub/sqlcmd is an action that runs script containing the languages and commands supported by SQL Server SQLCMD.

## Supported methods
- **Authentication**: windows authentication

## Parameters
```YAML
- uses: snsinahub/dotnet-cli@v1.0.0
  with:   
    
    # Type of command
    # supported values
    # script: pass sql script file to the action
    # example:
    #   sqlcmd_action: "script"
    sqlcmd_action: "script"
    
    # Absolute path to sql file
    # example:
    #   sql_path: 'C:\scripts\run.sql'
    sql_path: 'C:\scripts\run.sql' 
    
    # Name of sql server URL or Machine name
    # example:
    #   server_name: 'C:\project'
    server_name: "sql.snsinahub.com"
    
    # Pass parameters in format of comma separated values
    # IMPORTANT: if you need to put value of each variable inside quotes please follow      #   
    #   sqlcmd_variables: env='dev' account='dev-account'
    #   input_type: inline
    sqlcmd_variables: env='dev' account='dev-account'


    # Pass parameters in format of comma separated values
    # IMPORTANT: if you need to put value of each variable inside quotes USE SINGLE QUOTES ONLY 
    # DOUBLE QUOTES ARE NOT ACCEPTED
    # example:
    #   input_type: inline
    input_type: inline
    
    # Query Timeout
    # example:
    #   query_timeout: 6000
    query_timeout: 6000
    
    # MS SQL Server database name
    # example:
    #   db_name: SSISDB
    db_name: SSISDB
```

## Example
```YAML
- name: sqlcmd scripts
  uses : snsinahub/sqlcmd@v1.0.0
  with:
    sqlcmd_action: "script"
    sql_path: 'C:\scripts\run.sql' 
    server_name: "sql.snsinahub.com"
    sqlcmd_variables: env='dev' account='dev-account'
    input_type: inline
    query_timeout: 6000
    db_name: SSISDB
```