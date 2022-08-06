# Current Lib
The `power` table contains functions that enable machinery to use a unique power system.

It is important for any power using script to have this at the top:

* `require "/scripts/power.lua"`

And for any power using object to have this in their `init` hook:

* `message.setHandler("current", power.handler)`

---

#### `void` power.setMaxPower(`Number` amount)

Sets the maximum power capacity of an object. It is recommended for this to be in the `init` hook, however it can go wherever as long as it's defined before any other power functions are called.

---

#### `void` power.setPower(`Number` amount)

Sets the current power of an object. This will be clamped between 0 and the maximum power capacity.

---

#### `number` power.addPower(`Number` amount)

Adds an amount of power to the current power of an object. It will return a number that is the amount of power added.

---

#### `boolean` power.takePower(`Number` amount)

Takes an amount of power from the current power of an object. It will return a boolean whether or not it can take the amount of power required.

---

#### `boolean` power.pushPower(`Number` wireNodeID, `Number` amount)

Takes an amount of power from an object and gives it to another object(s) connected to a node. If multiple objects are connected to the same node, it will split the power evenly.
It will return a boolean whether or not it can take the amount of power required.

---

#### `number` power.getMaxPower(`Number` amount)

Returns the maximum power capacity an object has.

---

#### `number` power.getPower(`Number` amount)

Returns the amount of power an object has.
