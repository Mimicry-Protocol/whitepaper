# 💻 In-App Use Cases

### **Fee Settlement**

Players may use a wide array of ERC-20 tokens to [open positions](../core-mechanics/), pay [exit fees](../fees.md#exit-fees), and [tip](../fees.md#balancer-fees) Balancers. And Directors may use whatever token they like to pay for [advertising](../fees.md#advertising-fees). However, all exit fees, advertising fees, and tips must ultimately be paid using $MIMIC. Accordingly, when a player does not pay fees with $MIMIC, their payment token will be immediately converted to a _MARKET BUY_ order for $MIMIC tokens across supported exchanges and they will be responsible for slippage. Therefore every action in the protocol represents demand for $MIMIC.&#x20;

For the sake of clarity, only fees—not deposits locked in the smart contract—will be converted to $MIMIC.&#x20;

### **Feature Gates**

Players who use $MIMIC to open positions, or auto-swap to $MIMIC within our UI, will have access to advanced features that will not be available to players who use other tokens. For example, [automations](../advanced-features/automations/) will all be restricted to players who mint Mimes using $MIMIC.&#x20;

Community rewards will also be restricted to players who use $MIMIC to open their positions. This will serve to increase demand for the token while also effectively removing $MIMIC tokens from circulation when they are locked in positions.
