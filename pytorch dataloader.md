pytorch dataloader:

将图片和标签成对组织起来，然后送入网络

```class
class MyData(Dataset):
	def __init__(self, csv, resize2size)
		self.size = resize2size
		sourceFile = open(csv, 'r')
		img_lb = []
		for line in sourceFile:
			img_lb.append((line[0], float(line[3])))
		self.img_lb = img_lb
	
	def transform(self, img, ang):
		# flip, resize2(self.size, self.size), rotate
        p = np.random.rand(1)
        if p >= 0.5:
            img = img.transpose(Image.FLIP_LEFT_RIGHT)
            ang = -ang
        
        # rotate
        angle = np.random.uniform(-10, 10)
        img.rotate(angle)
        
        transform_img = transforms.Compose([transforms.Resize((self.size, self.size)),
                                            transforms.ToTensor()])
        img = transform_img(img)
        
        return img, ang
		
	def __getitem__(self, index):
		imgName, ang = self.img_lb[index]
		img = Image.open(imgName)
		img, ang = self.transform(img, ang)
		return img, ang
	
	def __len__(self):
		return len(self.img_lb)
	
if __name__ == "__main__":
    train_data = MyData(csv="D:\Prj\python_Prj\e2e_prj\udacity_data\turnleft\driving_log.csv",120)
    train_data_loader = DataLoader(train_data, batch_size=256, shuffle=True)
	
	
```

