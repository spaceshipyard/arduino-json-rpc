# Arduino JSON RPC
Arduino json communication library, for remote procedure calls, it is based on https://github.com/bblanchon/ArduinoJson

<<<<<<< HEAD
Example of usage:
=======
sample of input:

```{ "cmd": "sum", "params": { "a": 1, "b": 2 }, "id": "reqId1" }``` `\n`

sample of output:

```{ "cmd": "acknowledge", "params": { "sum": 3 } , "replyOn": "reqId1" , "replyStatus": 0, "replyDelay": 1 }``` `\n`

>>>>>>> 889aec675e52131659e8f5636e3f0217fab6b7f1

```
//#include <Arduino.h> //it is required in cause of compilation under platform.io
#include <ArduinoJsonRpc.h>


CommandResult echoCmdHandler(const JsonObject& inParams, JsonObject& outParams) {
  //outParams["msg"] = inParams["msg"]; // or following 
  for (auto kv : inParams) {
    outParams[kv.key] = kv.value;
  }

  return processed;
}

void setup() {
  Serial.begin(9600);
  while (!Serial) {
    // wait serial port initialization
  };
  attachCommandProcessor("echo", &echoCmdHandler);
}

void loop() {
  tryToReadNextCmd(Serial);
}


```
