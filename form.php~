<h1>Simpelt spørgeskema</h1>

<!-- Formular -->
<form action="#" method="get" enctype="multipart/form-data">
	<!-- tekst -->
	Navn <input type="text" name="navn" value="navn"><br>
	
	<!-- radio buttons -->
	Hvordan er dit humør i dag? ( 1 er rigtig godt, 5 er træls )
		1 <input type="radio" name="humoer" value="1">
		2 <input type="radio" name="humoer" value="2">
		3 <input type="radio" name="humoer" value="3">
		4 <input type="radio" name="humoer" value="4">
		5 <input type="radio" name="humoer" value="5"><br>
		
	<!-- valgmuligheder -->
	<select name="pc">
		<option value="mac">Mac</option>
		<option value="linux">Linux</option>
		<option value="windows">Windows</option>
	</select>
	<br>

	<!-- dato (prøv andre input types) -->
	<input id="date" name="date"><br>
	
	<br>
	
	<!-- ok, fortryd -->
	<button name="OK" value="ok" type="submit">OK</button>
	<button name="Fortryd" value="fortryd" type="reset">Fortryd</button>
</form>

<!-- javascript: feedback til brugeren -->
<script>
	// JavaScript tjekker før noget sendes til en server!

	// lokal client dato i formfield via DOM
	document.getElementById('date').value = Date();
	
	var dato = new Date();
	
	var aar = dato.getFullYear();
	var maaned = dato.getMonth();
	var dag = dato.getDay();
	
	ugedag = [
		"Søndag",
		"Mandag",
		"Tirsdag",
		"Onsdag",
		"Torsdag",
		"Fredag",
		"Lørdag"	
	];
	
	// gentag med måned, husk at arrays tælles fra 0!
	
	console.log( "Dato: " + ugedag[dag] + " " + maaned + " " + aar )	
	
	// skriv en mere elegant dato til datofeltet: dag, måned, år
	
	// test input
	// @link: http://www.w3schools.com/js/tryit.asp?filename=tryjs_validation_js
</script>

<!-- output fra php herfra -->
<?php
/**
 * Behandler form data
 * hvis nogen har klikket ok
 */
if ( isset( $_GET['OK'] ) ){
	
	echo "<pre>"; // viser objektet pænere
	
	print_r( $_GET ); // formdataobjekt

	echo "</pre>";
	
}


/**
 * Gemmer til en fil i et array
 * @link: $myfile = fopen("newfile.txt", "w") or die("Unable to open file!");
 */
 
/*
$myfile = fopen("newfile.txt", "w") or die("Unable to open file!");
$txt = "Hello World!";

fwrite($myfile, $txt);
fwrite($myfile, $txt);
fclose($myfile);
*/

/**
 * Lav en funktion, der gemmer data svarene fra $_GET
 * vi gemmer det som et array i et array
 */
function gemSvar( $navn, $humoer ){
	
	// @link: http://php.net/manual/en/function.fopen.php
	$myfile = fopen("newfile.txt", "a+") or die("Filen kan ikke åbnes!");
	
	$navn = strip_tags( $navn ); // fjerner html tags
	fwrite( $myfile, "\n----" ); // ny linje + navn
	fwrite( $myfile, "\n" . $navn ); // ny linje + navn
	fwrite( $myfile, "\nHumør: " . $humoer );
	// tilfoej resten af formularen herfra
	
	fclose($myfile);

}

if ( isset( $_GET['OK'] ) ){

	gemSvar($_GET['navn'], $_GET['humoer']); // funktionen fyres af ...
	
	echo "Tak for dit svar!";
	
}

?>