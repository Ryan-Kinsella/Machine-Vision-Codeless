# Machine-Vision-Codeless
### *Due to the course content being reused, the code associated will be not be included in this repository. If you'd like to view the code, please request access to view as a colaborator in my other repository, Ryan-Kinsella/Machine-Vision.*

## (ELEC 474) Machine Vision using C++ and linked library OpenCV to solve image recognition/filtering problems. 
*Each cpp file has int main() and all files should be excluded from the build besides the one you're wanting to run.*

### Project.cpp files:
#### The project is to create a panoramic image from a series of overlapping images of a scene. This task is divided into three steps. The first step is to extract features from the images, and automatically establish feature correspondences between image pairs. The second step is to use these correspondences to estimate transformations between each image, and establish the most likely transformations between the image pairs. The third step is to apply these transformations to compose a single composite image from all images. I made 3 versions of this project (labeled V1-V3), each improving the runtime and complexity. 
![proj](https://user-images.githubusercontent.com/46120322/73096637-44a5b500-3eb3-11ea-806c-0056701f47e9.JPG)

### Project_V1_translateImg.cpp:
#### Matches and stitched images can clearly be seen drawn on large canvases. The time and space complexity beyond 10 matches became too much to compute, since each time the canvas needed to multiply in size. 
![V1](https://user-images.githubusercontent.com/46120322/73096642-48393c00-3eb3-11ea-86e5-1174f41a5424.JPG)

### Project_V2_without_class.cpp:
#### Created new logic that has a dynamically growing canvas based on the end-point x size of the stitched image. Still the runtime was ~45 seconds, without reusing calculations. The performance of this version was the best since each iteration the stitched image was compared to every available image to determine the best match. 
![V2 4](https://user-images.githubusercontent.com/46120322/73098870-4625ac00-3eb8-11ea-9977-0d72aa01748c.JPG)
![V2 2](https://user-images.githubusercontent.com/46120322/73096649-4a9b9600-3eb3-11ea-8175-3249bc57d6e2.JPG)
![V2](https://user-images.githubusercontent.com/46120322/73096662-4ff8e080-3eb3-11ea-80dd-c788d76fe1aa.JPG)
![V2 3](https://user-images.githubusercontent.com/46120322/73097380-0f01cb80-3eb5-11ea-8cf5-b490f5023fee.JPG)

### Project_V3_Final_Classes.cpp:
#### Created 'Image' class whos constructor loads the Mat img, keypoints and decriptors, bool 'is stitched' logic along with other helpful simple to implement tools. The runtime has become ~7 seconds, and has been able to reuse keypoint/descriptor calculations. I attempted to add a cretiera that takes the leftmost keypoint to try to stitch images left to right since that's how my logic is set up, however this didn't end up improving the performance. 
![V3](https://user-images.githubusercontent.com/46120322/73096679-5424fe00-3eb3-11ea-99e3-6bb6fc0d6d70.JPG)

# Labs:

### lab2.cpp:
#### Using the contours of a background subtracted image, identify and issoloate only the contours of six different parts (given in jpeg format) moving through an assembly line. Accuracies will also be shown. 
![Recording5](https://user-images.githubusercontent.com/46120322/68702263-82eb3380-0556-11ea-8687-803b5d2c77f6.gif)


### lab3.cpp:
#### Given four road images, identify the edges of the lane that the car should be in using a self-created RANSAC (random sample consensus) line extraction algorithm. Implement a circle RANSAC algorithm, and show the contours of the sun (fully enclosed cirlce) in an image with several plannets and stars. Implement an improvement on the previously mentioned RANSAC algorithm, with runtimes of each. 
![ransacEdges_1 2019-10-15 7_08_28 PM](https://user-images.githubusercontent.com/46120322/66879050-98d2fc00-ef8a-11e9-846d-62bc2d9fe877.png)

![ransacEdges_2 2019-10-15 7_07_50 PM](https://user-images.githubusercontent.com/46120322/66879054-9cff1980-ef8a-11e9-89f9-2531dca02787.png)

![ransacEdges_2 improved 2019-10-15 7_07_48 PM](https://user-images.githubusercontent.com/46120322/66879056-a12b3700-ef8a-11e9-970f-83b1324f905b.png)

![Canny_3 2019-10-15 7_07_39 PM](https://user-images.githubusercontent.com/46120322/66879062-a5efeb00-ef8a-11e9-9a3c-9037ca918582.png)

![Contours drawn 3 2019-10-15 7_07_35 PM](https://user-images.githubusercontent.com/46120322/66879065-aa1c0880-ef8a-11e9-84ee-842ab3eff4ae.png)

![ransacEdges_3 2019-10-15 7_07_28 PM](https://user-images.githubusercontent.com/46120322/66879066-ad16f900-ef8a-11e9-9683-2444617e8913.png)

![ransacEdges_3 2019-10-15 7_06_57 PM](https://user-images.githubusercontent.com/46120322/66879068-b2744380-ef8a-11e9-96e6-16e7b1dd362f.png)

![ransacEdges_4 2019-10-15 7_06_49 PM](https://user-images.githubusercontent.com/46120322/66879074-b607ca80-ef8a-11e9-84a0-ab0ee8d4d5e0.png)

![Canny Circle 2019-10-15 7_04_21 PM](https://user-images.githubusercontent.com/46120322/66879077-b99b5180-ef8a-11e9-9956-12a40772abae.png)

![Circle Ransac Edges 2019-10-15 7_04_15 PM](https://user-images.githubusercontent.com/46120322/66879080-bc964200-ef8a-11e9-8342-680bb20ea282.png)

![Circle Image with Ransac 2019-10-15 7_04_08 PM](https://user-images.githubusercontent.com/46120322/66879083-bf913280-ef8a-11e9-9ff4-166bc69c683c.png)

### lab4.cpp:
#### Create an object detection and pose estimation for a given pair of images. This will be implemented using a custom RANSAC_transform function to detect the number of inliers to produce the best transformation function to map the model to the scene. The custom RANSAC_transform function returning the best transformation matrix will be compared to the openCV's cv::estimateAffinePartial2D() function producing an estimate for the best transformation matrix. Outupts as images for estimateAffinePartial2D are shown as the dark blue border, RANSAC_transform() in the light blue rectangle, and outputs as transformation matrices in terminal are shown below. 

Box:
![C__Users_R-k-l_source_repos_ComputerVision_x64_Release_ComputerVision exe 2019-10-29 11_33_53 AM](https://user-images.githubusercontent.com/46120322/67783245-5b697680-fa40-11e9-86a7-ffffefb971a7.png)

![model_img 2019-10-29 11_52_54 AM](https://user-images.githubusercontent.com/46120322/67784796-ae442d80-fa42-11e9-9757-b88b874cdd11.png)

![blendedImg with estimate (thick border) and best_transformation_matrix (translucent rectangle) 2019-10-29 11_28_30 AM](https://user-images.githubusercontent.com/46120322/67783328-79cf7200-fa40-11e9-96d7-f06ab057b4d4.png)

Desk:
![C__Users_R-k-l_source_repos_ComputerVision_x64_Release_ComputerVision exe 2019-10-29 11_34_31 AM](https://user-images.githubusercontent.com/46120322/67783369-88b62480-fa40-11e9-9bb7-3ed8f66462d9.png)

![blendedImg with estimate (thick border) and best_transformation_matrix (translucent rectangle) 2019-10-29 11_29_29 AM](https://user-images.githubusercontent.com/46120322/67783413-953a7d00-fa40-11e9-8bc4-423810faa5ea.png)

Painting:
![C__Users_R-k-l_source_repos_ComputerVision_x64_Release_ComputerVision exe 2019-10-29 11_35_03 AM](https://user-images.githubusercontent.com/46120322/67783468-a6838980-fa40-11e9-8214-f7ede9880c82.png)

![blendedImg with estimate (thick border) and best_transformation_matrix (translucent rectangle) 2019-10-29 11_25_41 AM](https://user-images.githubusercontent.com/46120322/67783495-b3a07880-fa40-11e9-9cbe-ca45dbc4e75a.png)

### lab5.cpp:
#### Given a stereovision image pair, find their fundamental matrix, and print out the elements on the console. Select a series of points (by mouse click) in one image, and display the corresponding epipolar lines in the other image.
![Recording4](https://user-images.githubusercontent.com/46120322/68700824-9cd74700-0553-11ea-80db-732f56214fd7.gif)





