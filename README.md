# PhyscData
## 설명
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

메서드를 만든후 키의 평균을 for문으로 구한다.
```java
		// 키의 평균 값을 구함
	static double aveHeight(PhyscData[] dat) {
		double sum = 0;
			
		for(int i = 0; i < dat.length; i++)
			sum += dat[i].height;
		return sum / dat.length;
	}
```

메서드로 만든후 입력받은 배열을 통해 시력의 분포를 구함
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
입력한 값
```java
		PhyscData[] x = {
				new PhyscData("강민하", 162, 0.3),
				new PhyscData("김찬우", 173, 0.7),
				new PhyscData("박준서", 175, 2.0),
				new PhyscData("유서범", 171, 1.5),
				new PhyscData("이수연", 168, 0.4),
				new PhyscData("장경오", 174, 1.2),
				new PhyscData("황지안", 169, 0.8),
		};
```
위에서 만든 매서드와 입력된값을 출력한다.<br>
먼저 입력된 값을 출력하고 평균키를 출력한후 시력의 분포도를 출력한다.
```java
		int[] vdist = new int[VMAX];
		// 시력의 분포
		System.out.println("  신체 검사 리스트");
		System.out.println("이 름    키   시 력");
		System.out.println("---------------");
			
		for(int i = 0; i < x.length; i++) 
			System.out.printf("%-6s%3d%5.1f\n", x[i].name, x[i].height, x[i].vision);
			System.out.printf("\n평균키 : %5.1fcm\n", aveHeight(x));
			
			distVision(x, vdist);
			System.out.println("\n  시력 분포");
		for(int i = 0; i < VMAX; i++)
			System.out.printf("%3.1f~: %2d명\n", i / 10.0, vdist[i]);	
```
```java
class PysicalEx {
		
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
		// 키의 평균 값을 구함
		static double aveHeight(PhyscData[] dat) {
			double sum = 0;
			
			for(int i = 0; i < dat.length; i++)
				sum += dat[i].height;
			return sum / dat.length;
		}
		
		// 시력의 분포를 구함
		static void distVision(PhyscData[] dat, int[] dist) {
			int i = 0;
			dist[i] = 0;
			for(i = 0; i < dat.length; i++)
				if(dat[i].vision >= 0.0 && dat[i].vision <= VMAX / 10.0)
					dist[(int)(dat[i].vision * 10)]++;
		}
		
	public static void main(String[] args) {
			
			PhyscData[] x = {
					new PhyscData("강민하", 162, 0.3),
					new PhyscData("김찬우", 173, 0.7),
					new PhyscData("박준서", 175, 2.0),
					new PhyscData("유서범", 171, 1.5),
					new PhyscData("이수연", 168, 0.4),
					new PhyscData("장경오", 174, 1.2),
					new PhyscData("황지안", 169, 0.8),
			};
			int[] vdist = new int[VMAX];
			// 시력의 분포
			System.out.println("  신체 검사 리스트");
			System.out.println("이 름    키   시 력");
			System.out.println("---------------");
			
			for(int i = 0; i < x.length; i++) 
				System.out.printf("%-6s%3d%5.1f\n", x[i].name, x[i].height, x[i].vision);
				System.out.printf("\n평균키 : %5.1fcm\n", aveHeight(x));
				
				distVision(x, vdist);
				System.out.println("\n  시력 분포");
			for(int i = 0; i < VMAX; i++)
				System.out.printf("%3.1f~: %2d명\n", i / 10.0, vdist[i]);	
	}
}
```
## 결과
![image](https://user-images.githubusercontent.com/123055714/225803223-6805fc55-9616-493b-a90b-77c239a5451c.png)
