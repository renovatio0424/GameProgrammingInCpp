# chapter 6. 3D Graphics

## 3D 메시 그리기

### 3D Mesh? 
  A 3D mesh is the structural build of a 3D model consisting of polygons
  
[refer](https://www.researchgate.net/figure/3D-mesh-triangles-with-different-resolution-3D-Modelling-for-programmers-Available-at_fig2_322096576)

### 뷰-투영 행렬

뷰: 가상 카메라가 게임 세계를 바라보는 방법
투영: 가상 카메라의 시점으로부터 clipping space 로 변환하는 방법

[refer](https://www.charlezz.com/wordpress/wp-content/uploads/2018/12/ViewFrustum.png)

#### 뷰 행렬
look-at matrix
  1. 눈의 높이
  2. 눈이 바라보는 타깃 위치
  3. 눈의 수직 방향 
  
[refer](https://www.slideshare.net/AntonGerdelan/computer-graphics-lecture-03-virtual-cameras-and-the-transformation-pipeline)

#### 투영 행렬
3D 세계가 화면상의 2D 세계에 그려질 때 평평해지는 정도를 결정한다. 3D 게임에서는 2가지 타입의 투영 행렬이 존재한다
  1. 직교 투영 (orthographic projection)
    1. 뷰의 너비
    2. 뷰의 높이
    3. 가까운 평면과의 거리
    4. 먼 평면과의 거리
  2. 원근 투영 (perspective projection)
    1. 수평 시야각 (FoV, hotizontal Field Of View)
    
### Z-Buffering
#### 화가 알고리즘의 문제점
  1. 3D에서는 앞뒤 정렬이 정적이지 않다
  2. 불필요한 대량 그리기 연상 수정, 프레임마다 단일 픽셀에 여러번 색상을 덮어쓰는 문제
  3. 삼각형 겹치는 문제
  
#### z-buffering 
  Z 버퍼는 더 '가까운 물체가 더 먼 물체를 가린다' 라는 직관적 깊이 관념을 정확하게 따를 수 있게 돕는다
  
#### z-buffering 의 문제점
  투명한 오브젝트 그리기
