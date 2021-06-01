# Multimedia_Colorization
Gachon University's Department of Software 2021-1 Multimedia & Lab Class Project.<br/>
Our project is hint-based colorization. This is a project to color the model by inserting an input image with color hints.

# Team Member Info
- GeeSeung Park : 96sean@naver.com
- Hakyeong Kim : gkrudgkrud10@naver.com
- Yujin Song : j_jongleur@naver.com
- Siyeon Cho : chosiyeonn@gmail.com

# Experiments
We compared performance by creating three different models to build better performance models. </br>
The models we tried are UNet, Attention Unet, and Unet++.

|UNet|Attention Unet|UNet++
|---|---|---|
|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120272368-f21aab00-c2e7-11eb-9f92-3b95bcd3e0d5.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120272640-65242180-c2e8-11eb-93bb-78699369b15b.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120272708-7a994b80-c2e8-11eb-9b9c-28b5ce3b2e48.png">|  

<br/>After building each model of structure, we trained the model with training data and tested it.  
|UNet|Attention Unet|UNet++
|---|---|---|
|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120273369-6144cf00-c2e9-11eb-95e3-03094708f552.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120273413-6e61be00-c2e9-11eb-9bc3-0f00389f275f.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120273430-715cae80-c2e9-11eb-8bd2-7324f38f989f.png">|

<br/>Comparing the graph, we could get the highest performance result on Unet. Therefore, we decided to make our model based on the Unet structure.
After selecting the structure as Unet, we wanted to improve performance by changing the number of layers. I made 3 layers, 4 layers, 5 layers, and 6 layers, and the conditions of the rest were the same, and we got the results.

|Training dataset|Validation dataset
|---|---|
|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120274193-779f5a80-c2ea-11eb-952c-f76480d9a163.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120274212-7c640e80-c2ea-11eb-9c2b-ab343de7036b.png">|

<br/>In general, the more layers there are, the more they improve. Therefore, we proceeded with building a model with 6 layers.Next, we changed batch_size and compared the results.
|Training dataset|Validation dataset
|---|---|
|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120274707-30fe3000-c2eb-11eb-9c35-702235a157cd.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120274726-378ca780-c2eb-11eb-83a2-d786fe6921a0.png">|

<br/>Based on the results above, we found that batch_size 4 performs best. Next, we compared performance according to optimizer.
|Adam|Adadelta|Adagrad|SDG
|---|---|---|---|
|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120275229-f779f480-c2eb-11eb-866d-14c0f0bd1774.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120275233-f943b800-c2eb-11eb-93e5-a5323a966deb.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120275277-08c30100-c2ec-11eb-8157-019a3d80e4fd.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120275285-0bbdf180-c2ec-11eb-82bb-417c1eb80961.png">|


# Model
We tried to optimize the model by trying various things. The final model is as below.
* Unet based Model 
* Data batch_size : 4
* Data suffle : True
* loss : MSE 
* optimizer : Adam
* Epoch : 175

|Final Model PSNR|Final Model Loss
|---|---|
|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120275760-c2ba6d00-c2ec-11eb-98bb-6c3e61a63ae5.png">|<img width="250" alt="image" src="https://user-images.githubusercontent.com/63833392/120275771-c51cc700-c2ec-11eb-81f4-53c8d2521c4e.png">|

# Testing 
<p>
  <img height="200" src="https://user-images.githubusercontent.com/63833392/120275959-06ad7200-c2ed-11eb-96bf-c811035d990d.png"> &nbsp
  <img height="200" src="https://user-images.githubusercontent.com/63833392/120275970-0a40f900-c2ed-11eb-9473-8fc66469c8e4.png"> &nbsp
</p>
