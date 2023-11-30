# XO
# My first test project. I still don’t really understand how everything works here. I posted a tic-tac-toe game that I made a long time ago on JS. But for some reason only the code is displayed.
<html>
<head>
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
	<style type="text/css">
		td{
			width: 100px;
			height: 100px;
		}
		table{
			text-align: center;
			font-family: "Comic Sans MS";
			font-size: 50pt;
		}
	</style>
</head>
<body>
	<table border="1">
		<tr>
			<td id="n0" onclick="cl(0);"></td>
			<td id="n1" onclick="cl(1);"></td>
			<td id="n2" onclick="cl(2);"></td>
		</tr>
		<tr>
			<td id="n3" onclick="cl(3);"></td>
			<td id="n4" onclick="cl(4);"></td>
			<td id="n5" onclick="cl(5);"></td>
		</tr>
		<tr>
			<td id="n6" onclick="cl(6);"></td>
			<td id="n7" onclick="cl(7);"></td>
			<td id="n8" onclick="cl(8);"></td>
		</tr>
	</table>

	<script type="text/javascript">
		m = [" "," "," ",
			 " "," "," ",
			 " "," "," "];

		gameover = false;
		hod = "X";

		function cl(a) {
			if (m[a] == " " && gameover == false){
				m[a] = hod;
				el = document.getElementById('n'+a);
				el.innerHTML = hod;

				if (hod == "X"){
					hod = "O";
				} else {
					hod = "X";
				}

				if ((m[0] + m[1] + m[2] == "XXX") ||
			   		(m[3] + m[4] + m[5] == "XXX") ||
			   		(m[6] + m[7] + m[8] == "XXX") ||
			   		(m[2] + m[4] + m[6] == "XXX") ||
			   		(m[0] + m[4] + m[8] == "XXX") ||
			   		(m[0] + m[3] + m[6] == "XXX") ||
			   		(m[1] + m[4] + m[7] == "XXX") ||
			   		(m[2] + m[5] + m[8] == "XXX")) {
			   			gameover = true;
			   			alert("X win");
				} else

				if ((m[0] + m[1] + m[2] == "OOO") ||
			   		(m[3] + m[4] + m[5] == "OOO") ||
			   		(m[6] + m[7] + m[8] == "OOO") ||
			   		(m[2] + m[4] + m[6] == "OOO") ||
			   		(m[0] + m[4] + m[8] == "OOO") ||
			   		(m[0] + m[3] + m[6] == "OOO") ||
			   		(m[1] + m[4] + m[7] == "OOO") ||
			   		(m[2] + m[5] + m[8] == "OOO")) {
			   			gameover = true;
			   			alert("O win");
				} else
				{
					isEmpty = false;
					for (i=0; i<9; i++){
						if (m[i] == " "){
							isEmpty = true;
						}
					}

					if (isEmpty == false){
						gameover = true;
			   			alert("Draw");
					}
				}
			}
		}
	</script>
</body>
</html>
