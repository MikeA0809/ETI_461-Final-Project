# ETI_461-Final-Project
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
<link href="Name.css" rel="stylesheet" type="text/css">
</head>
<body>
<section><img src="../../../Users/Micha/OneDrive/Pictures/Hulu/hulu-logo.png" width="1037" height="277" alt=""/>
  
</section>
<form action="#insert.php" method="POST">
	ID: <input type="number" name="id">
	<br>
	Title: <input type="text" name="title"> <br>
	Genre: <input type="text" name="genre"> <br>
	Release Year: <input type="number" name="release_year"> <br>
	Director:  <input type="text" name="director"> <br>
	Studio: <input type="text" name="studio"> <br>
	Rating: <input type="number" name="rating"> <br>
	<input type="submit" value="Rent"> 
	
	
</form>
	<body>
  
  <main>
    <section id="featured-movies">
      <p>Movies To Rent</p>
      <ul>
        <li>
		  <img src="../../../Users/Micha/OneDrive/Pictures/Hulu/fanart-avengers-endgame-poster-re-edit-with-some-of-the-v0-a1h3w7blmm2a1.jpg" width="138" height="205" alt=""/>
		  <h3> Avengers: Endgame</h3>
			<p>ID: 1</p>
			<p>Genre: Action/Superhero</p>
          <p>Release Year: 2019</p>
          <p>Director: Anthony Russo and Joe Russo</p>
			<p>Studio:  Marvel Studios</p>
          <p>Rating: 8</p>
        </li>
        <li><img src="../../../Users/Micha/OneDrive/Pictures/Hulu/image.jpg" width="150" height="200" alt=""/>
          <h3> Parasite</h3>
          <p>ID: 2</p>
			<p>Genre: Thriller/Drama</p>
          <p>Release Year: 2019</p>
          <p>Director:  Bong Joon-ho</p>
			<p>Studio:  Barunson E&A Corp</p>
          <p>Rating: 9</p>
        </li>
        <li><img src="../../../Users/Micha/OneDrive/Pictures/Hulu/1-9504542592.jpg" width="154" height="215" alt=""/>
			<h3> Irishman</h3>
          <p>ID: 3</p>
			<p>Genre: Crime/Drama</p>
          <p>Release Year: 2019</p>
          <p>Director: Martin Scorsese</p>
			<p>Studio:  Netflix</p>
          <p>Rating: 8</p>
        </li>
      </ul>
    </section>
    <section id="popular-movies">
      <h2>Popular Movies</h2>
      <ul>
        <li><img src="../../../Users/Micha/OneDrive/Pictures/Hulu/MV5BNGVjNWI4ZGUtNzE0MS00YTJmLWE0ZDctN2ZiYTk2YmI3NTYyXkEyXkFqcGdeQXVyMTkxNjUyNQ@@._V1_.jpg" width="138" height="200" alt=""/>
          <h3> Joker</h3>
         <p>ID: 4</p>
			<p>Genre: Crime/Drama</p>
          <p>Release Year: 2019</p>
          <p>Director:  Todd Phillips</p>
			<p>Studio:   Warner Bros. Pictures</p>
          <p>Rating: 7</p>
        </li>
        <li><img src="../../../Users/Micha/OneDrive/Pictures/Hulu/MV5BMGUwZjliMTAtNzAxZi00MWNiLWE2NzgtZGUxMGQxZjhhNDRiXkEyXkFqcGdeQXVyNjU1NzU3MzE@._V1_.jpg" width="136" height="200" alt=""/>
          <h3> Knives Out</h3>
         <p>ID: 5</p>
			<p>Genre: Mystery/Comedy</p>
          <p>Release Year: 2019</p>
          <p>Director: Rian Johnson</p>
			<p>Studio: Lionsgate</p>
          <p>Rating: 10</p>
        </li>
        <li><img src="../../../Users/Micha/OneDrive/Pictures/Hulu/MV5BMjUxMDQwNjcyNl5BMl5BanBnXkFtZTgwNzcwMzc0MTI@._V1_.jpg" width="138" height="205" alt=""/>
          <h3>Get Out</h3>
          <p>ID: 6</p>
			<p>Genre: Horror/Thriller</p>
          <p>Release Year: 2017</p>
          <p>Director:  Jordan Peele</p>
			<p>Studio: Universal Pictures</p>
          <p>Rating: 7</p>
        </li>
      </ul>
    </section>
  </main>
  <footer>
<p>&copy; 2023 Movie Database. All rights reserved.</p>
	
	
</body>
</html>
	
	

<?php
 
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "hulu";
 
// Create connection
$conn = new mysqli($servername,
    $username, $password, $dbname);
 

 
$sqlquery = "INSERT INTO renter(id, title, genre, release_year, director, studio, rating) values ('$id', '$title', '$gnere', '$release_year', '$director', '$studio', '$rating')";
 



 
if ($_SERVER["REQUEST_METHOD"] == "POST") {
 
    // collect value of input field
    $data = $_REQUEST['val1'];
 
    if (empty($data)) {
        echo "data is empty";
    } else {
        echo $data;
    }
}

 
 
?>
	
	
	<!DOCTYPE html>
<html>
 
<head>
    <title>Insert Page page</title>
</head>
 
<body>
    <center>
			<?php
 
      
        $conn = mysqli_connect("localhost", "root", "", "hulu");
         
        // Check connection
        if($conn === false){
            die("ERROR: Could not connect. "
                . mysqli_connect_error());
        }
         
        // Taking all 8 values from the form data(input)
        $id = $_POST['id'];
		$title = $_POST['title'];
		$genre = $_POST['genre'];
		$release_year = $_POST['release_year'];
		$director = $_POST['director'];
		$studio =$_POST['studio'];
		$rating =$_POST['rating'];
	
         
        // Performing insert query execution
        // here our table name is college
        $sql = "INSERT INTO college  VALUES ('$id',
            '$title','$genre','$release_year','$director','$studio','$rating')";
         
        if(mysqli_query($conn, $sql)){
            echo "<h3>data stored in a database successfully."
                . " Please browse your localhost php my admin"
                . " to view the updated data</h3>";
 
        
        ?>
    </center>
</body>
 
</html>



	
