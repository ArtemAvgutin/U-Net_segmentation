# U-Net_segmentation
## Segmentation of images with pets using neural networks.  / Сегментация изображений с домашними животными, используя нейросети.
### Задача: Реализовать алгоритм сегментации на основе нейросетей семейства u-net, используя библиотеки cv2, keras (Conv2D, MaxPooling2D, UpSampling2D), numpy и tensorflow.
### Результат: Были реализованы модели нейросетей u-net и MobileNetV2 с точностью - .
### Стек технологий: cv2, keras (Conv2D, MaxPooling2D, UpSampling2D), numpy и tensorflow.

#### Мы будем использовать набор данных домашних животных Oxford-IIIT. Он содержит 37 классов собак и кошек, по 200 изображений на каждый класс. Набор данных содержит метки в виде ограничивающих рамок и масок сегментации. Общее количество изображений в датасете 7349 картинок.
* [Датасет является популярным  для задачи сегментации изображений на соревнованиях Kaggle](https://www.kaggle.com/datasets/tanlikesmath/the-oxfordiiit-pet-dataset). Этот набор данных содержит изображения различных пород кошек и собак с разметкой сегментации, где каждое изображение снабжено маской, определяющей области, соответствующие животному на фотографии.

#### Результат работы u-net / Result of u-net work
![image](https://github.com/ArtemAvgutin/U-Net_segmentation/assets/131138862/b621d95c-5ffa-47eb-bb1b-00b9633ebe58)

#### Результат работы MobileNetV2 / Result of MobileNetV2
![image](https://github.com/ArtemAvgutin/U-Net_segmentation/assets/131138862/b6381523-2e48-4b4d-a1fc-5da658196d17)

#### Точность и потери при обучении / Accuracy and training loss
![image](https://github.com/ArtemAvgutin/U-Net_segmentation/assets/131138862/847aae35-cc6d-4470-99d3-28900f69899b)

#### Модель U-Net — это простая полностью сверточная нейронная сеть, которая используется для бинарной сегментации, т. е. классификации переднего плана и фона по пикселям. В основном состоит из двух частей. 
* Contracting Path: мы применяем серию конверсионных слоев и слоев понижающей дискретизации (максимальное объединение) слоев, чтобы уменьшить пространственный размер.
* Expanding Path: мы применяем серию слоев повышения дискретизации для восстановления пространственного размера входных данных.
* Две части соединяются с помощью слоев конкатенации между разными уровнями. Это позволяет изучать различные функции на разных уровнях. В конце у нас есть простой слой conv 1x1, чтобы уменьшить количество каналов до 1.
* Устройство U-Net включает в себя сверточные слои для извлечения признаков изображения и слои декодера для восстановления пространственной информации. Основное отличие модели U-Net заключается в использовании пути сопоставления, который позволяет сохранять пространственную информацию при уменьшении размерности изображения.
* Также в задачу входит создание сети MobileNetV2. MobileNetV2 — следующее поколение нейросетей этого семейства, которое позволяет достигать примерно такой же точности распознавания при ещё большей скорости работы.

### Task: Implement a segmentation algorithm based on neural networks of the u-net family, using the libraries cv2, keras (Conv2D, MaxPooling2D, UpSampling2D), numpy and tensorflow.
### Result: The u-net and MobileNetV2 neural network models were implemented with an accuracy of - .
### Technology stack: cv2, keras (Conv2D, MaxPooling2D, UpSampling2D), numpy and tensorflow.

#### The U-Net model is a simple fully convolutional neural network that is used for binary segmentation, i.e., pixel-wise classification of foreground and background. Mainly consists of two parts.
* Contracting Path: We apply a series of conversion and downsampling (max pooling) layers to reduce the spatial size.
* Expanding Path: We apply a series of upsampling layers to restore the spatial extent of the input data.
* The two parts are connected using layers of concatenation between different levels. This allows you to study different functions at different levels. At the end we have a simple 1x1 conv layer to reduce the number of channels to 1.
* The U-Net device includes convolutional layers to extract image features and decoder layers to recover spatial information. The main difference of the U-Net model is the use of a mapping path, which allows it to preserve spatial information while reducing image dimensionality.
* The task also includes creating the MobileNetV2 network. MobileNetV2 is the next generation of neural networks of this family, which allows you to achieve approximately the same recognition accuracy at an even higher operating speed.

#### We will use the Oxford-IIIT pet dataset. It contains 37 classes of dogs and cats, with 200 images per class. The dataset contains labels in the form of bounding boxes and segmentation masks. The total number of images in the dataset is 7349 images.
* [The dataset is popular for the image segmentation task in Kaggle competitions](https://www.kaggle.com/datasets/tanlikesmath/the-oxfordiiit-pet-dataset). This dataset contains images of different breeds of cats and dogs with segmentation labels, where each image is provided with a mask that defines the regions corresponding to the animal in the photo.
