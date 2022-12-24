
--we use modifier.py to modify the constraints we got from ERAN to some understandable format 

	we get input_modified.txt from input_unmodified.txt (input layer constraints)
	we get internal_modified.txt from internal_unmodified.txt (internal layer constraints)
	we get output_modified.txt from output_unmodified.txt (output layer constraints)

For this use command :  ./commands.sh

--z3_format_converter.py convert modified constrainsts to z3 understandable format 
  as well as solve some necessary constrainsts and returns a model. model have eta
  values corresp 

--parsing.py is called from z3_format_converter.py and parse file 
--To create real images from pixels we use create_actual_image.py

--deep.py is a python file which contains main function and will read the arguments on command line 
  and call appropriate functions.

--arguments : dataset, network name, etc.


Command : python3 deep.py mnist_relu_3_50.tf mnist output_modified.txt internal_modified.txt
											
		            (main file) (network file)   (dataset)  (output layer cons)(internal layer cons)






dont be fooled by mnist as dataset as in code bhaiya is using mnist_test.csv
#mnist is just saying deepzono to state that we are using it on mnist


eta_dash is eta values when z3 is used to solve

eta_dd is eta value when forward propagation is used



first_eta is text file used to store  z3 eta values which is later consumed to convert it into dictionary