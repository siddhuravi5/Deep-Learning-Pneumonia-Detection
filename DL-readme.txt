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

model-4 
	
	Increased validation set size
	added more conv,pooling and fully connected layers
	added more dropout layers with rate=0.5 
	
	A Sequential Keras Moidel
	Conv layer
	Pooling Layer
	Conv layer
	Pooling Layer
	Conv layer
	Pooling Layer
	Flatten
	Dropout 0.5
	Dense Layer 128
	Dropout 0.5
	Dense Layer 64
	Dropout 0.5
	Dense Layer 32
	Dropout 0.5
	Dense 1 sigmoid

	Adam optimizer
	binary crossentropy loss function

	Image Augmentaion done using tf.keras.preprocessing.image.ImageDataGenerator 
	with rescale=1.0/255,shear_range=0.2,zoom_range=0.2 and horizontal_flip=True 
	as parameters

	45 epochs
	batch-size : 32
	img size 32 * 32

	training loss : 0.092
	training accuracy : 0.96

	test loss : 0.2512
	test accuracy : 0.9433

model-5: Transfer Learning
	Sequence model of :
		VGG16 (top layer is popped, and freezed the weights)
		Dropout(0.25)
		Dense 128 Relu
		Dropout(0.25)
		Dense 1 Sigmoid

	50 epochs
	(128,128,3) image sizes
	batch-size : 64

	training loss : 0.1604
	training accuracy : 0.9382

	test loss : 0.2544
	test accuracy : 0.9188

model-6 : transfer learning 2
	Sequence model of:
	VGG16- 	pretrained weights for first 14 layers and then random
		weights for remaing 6 layers,
		all the layers are trainable
	Dropout(0.3)
	Dense 1 Sigmoid

	100 epochs
	(128,128,3) image sizes
	batch-size : 64

	training loss : 0.0371
	training accuracy : 0.9876

	test loss : 0.2559
	test accuracy : 0.9400

	