# FluentBit-confs

## Input

Read container logs from AWS EKS 

## Parser
```
[PARSER]
    Name docker_json
    Format json
    Time_Key time
    Time_Keep On
    Time_Format %Y-%m-%dT%H:%M:%S.%L
    # Command      |  Decoder | Field | Optional Action
    # =============|==================|=================
    Decode_Field_As json log
```
 ## Filter
 
Use K8s filter to add k8s realted info the to logs.

Use `Nest` filter to remove the default key appended by Fluent-Bit

## Output

Make sure that TLS is enabled, and the recieving ends key etc is properly populated here.

For debugging use `stdout`
