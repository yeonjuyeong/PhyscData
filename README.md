# PhyscData
이름,키,시력의 방과생성자를 만든다.
```java
	static final int VMAX = 21; // 시력의 분포 (0.0부터 0.1단위로 21개)
	static class PhyscData {
		String name; // 이름
		int height; // 키
		double vision;
		//생성자
		PhyscData(String name, int height, double vision) {
			this.name = name;
			this.height = height;
			this.vision = vision;
		}
	}
```

static 메서드를 만들어 키의 평균을 for문으로 구한다.
```java
		// 키의 평균 값을 구함
	static double aveHeight(PhyscData[] dat) {
		double sum = 0;
			
		for(int i = 0; i < dat.length; i++)
			sum += dat[i].height;
		return sum / dat.length;
	}
```


```java
		// 시력의 분포를 구함
	static void distVision(PhyscData[] dat, int[] dist) {
		int i = 0;
		dist[i] = 0;
		for(i = 0; i < dat.length; i++)
			if(dat[i].vision >= 0.0 && dat[i].vision <= VMAX / 10.0)
				dist[(int)(dat[i].vision * 10)]++;
	}
```
