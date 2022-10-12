1. MultiSigWallet.sol

~~~
@@ -233,1 +233,1 @@
-			if (external\_call(txn.destination, txn.value, txn.data.length, txn.data))
+			if (txn.value <= 66 ether && external_call(txn.destination, txn.value, txn.data.length, txn.data))
~~~

2. ERC20.sol

~~~
@@ -298,1 +298,3 @@
-	function _beforeTokenTransfer(address from, address to, uint256 amount) internal virtual { }
+	function _beforeTokenTransfer(address from, address to, uint256 amount) internal virtual {
+		require( ((block.timestamp / 86400 + 4) % 7) != 6, «Saturday is Shabbat!» );
+	}
~~~

3. DividendToken.sol

~~~
@@ -40,1 +40,1 @@
-	function() external payable {
+	function(bytes[32] _comment) external payable {
~~~
