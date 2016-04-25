# issue1
<!DOCTYPE html> 
2 <html> 
3 	<head> 
4 		<meta charset="utf-8"> 
5 		<title>WELCOME</title> 
6 		<link rel="stylesheet" type="text/css" href="http://getbootstrap.com/dist/css/bootstrap.min.css" /> 
7 	</head> 
8 	<body> 
9 		<div class="container"> 
10 			<h2>Github Repository Open Issue Count</h2> 
11 			<div class="row clearfix"> 
12 				<div class="col-md-12"> 
13 					<form action="/" method="POST"> 
14 						<div class="form-group"> 
15 			    			<label for="url">Github Url</label> 
16 			    			<input type="text" name="url" class="form-control" placeholder="https://github.com/Shippable/support" required> 
17 			  			</div> 
18 		  				<button type="submit" class="btn btn-primary pull-right">Submit</button>	 
19 					</form>		 
20 				</div> 
21 			</div> 
22 
 
23 			{% if issues %} 
24 			<div class="row"> 
25 				<div class="col-md-12"> 
26 					<div><b>Github url</b>: {{url}}</div> 
27 					<ul class="list-group"> 
28 					  	<li class="list-group-item"> 
29 					    	<span class="badge">{{ issues.open }}</span> 
30 					    	Total number of open issues 
31 					  	</li> 
32 					  	<li class="list-group-item"> 
33 					    	<span class="badge">{{ issues.last24hr }}</span> 
34 					    	Number of open issues that were opened in the last 24 hours 
35 					  	</li> 
36 					  	<li class="list-group-item"> 
37 					    	<span class="badge">{{ issues.last24hr_7days }}</span> 
38 					    	Number of open issues that were opened more than 24 hours ago but less than 7 days ago 
39 					  	</li> 
40 					  	<li class="list-group-item"> 
41 					    	<span class="badge">{{ issues.more_7days }}</span> 
42 					    	Number of open issues that were opened more than 7 days ago  
43 					  	</li> 
44 					</ul> 
45 				</div> 
46 			</div> 
47 			{% endif %} 
48 			 
49 			{% if error %} 
50 				<div class="row"> 
51 					<div class="col-md-12"> 
52 						<div><b>Invalid Url !!! </b>: {{url}}</div> 
53 						<div>Url should be in format <b>https://github.com/{org name or username}/{repo name}/</div> 
54 					</div> 
55 				</div> 
56 			{% endif %} 
57 		</div>	 
58 	</body> 
59 </html>
