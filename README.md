#### Face-Detection-with-Opencv

1) look at a picture and find all the faces in it

To find faces in this HOG image, all we have to do is find the part of our image that looks the most similar to a known HOG pattern that was extracted from a bunch of other training faces:

 ![Screenshot (194)](https://user-images.githubusercontent.com/82256818/170651487-d86c3d79-0319-4588-a63f-f439eb4f5d73.png)
 
 
2) focus on each face and be able to understand that even if a face is turned in a weird direction or in bad lighting, it is still the same person.
3) be able to pick out unique features of the face that you can use to tell it apart from other people— like how big the eyes are, how long the face is, etc.

![Screenshot (195)](https://user-images.githubusercontent.com/82256818/170651614-c8c1bea5-0f2c-4dc1-83b2-205c4f2e1b75.png)

The basic idea is we will come up with specific points (called landmarks) that exist on every face — the top of the chin, the outside edge of each eye, the inner edge of each eyebrow, etc. Then we will train a machine learning algorithm to be able to find these 68 specific points on any face:

The solution is to train a Deep Convolutional Neural Network. But instead of training the network to recognize pictures objects like we did last time, we are going to train it to generate 128 measurements for each face.

The training process works by looking at 3 face images at a time:

1) Load a training face image of a known person
2) Load another picture of the same known person
3) Load a picture of a totally different person
4) compare the unique features of that face to all the people you already know to determine the person’s name.
 
![Screenshot (197)](https://user-images.githubusercontent.com/82256818/170652238-bbb359a0-5eb8-46c7-bb1b-6ffc22e015ee.png)
