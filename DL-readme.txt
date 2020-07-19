model-1
	A Sequential Keras Moidel
	Conv layer
	Pooling Layer
	Conv layer
	Pooling Layer
	Flatten
	Dense Layer
	Dense Layer

	Adam optimizer
	binary crossentropy loss function

	Image Augmentaion done using tf.keras.preprocessing.image.ImageDataGenerator 
	with rescale=1.0/255,shear_range=0.2,zoom_range=0.2 and horizontal_flip=True 
	as parameters

	25 epochs
	batch-size : 32

	training loss : 0.1080
	training accuracy : 0.9582

	test loss : 0.2771
	test accuracy : 0.9086

	there is a need for improvement in both bias and variance

model-2
	added dropout regularization		
	
	A Sequential Keras Moidel
	Conv layer
	Pooling Layer
	Conv layer
	Pooling Layer
	Flatten
	Dropout, rate=0.15
	Dense Layer
	Dropout, rate=0.15
	Dense Layer

	loading the weights from model-1

	Did 25 more epochs (50 epochs)
	batch size : 32
	
	training loss : 0.0891
	training accuracy : 0.9664

	test loss : 0.3709
	test accuracy : 0.9071

	Training bias has reduced , but not the variance

model-3

	loaded the architecture from model-2
	not loading the weights
	only 25 epochs to reduce overfitting
	batch size : 32

	training loss : 0.1048
	training accuracy : 0.9605

	test loss : 0.3062
	test accuracy : 0.9087
