
#### lower_bound 
- 일종의 이진탐색으로 정렬된 데이터에서만 가능
- (시작위치, 끝위치, 찾고자 하는 데이터)
- 찾고자 하는 데이터가 8일 경우 8 이상인 값이 처음 나오는 위치를 구한다
- Ex)
	- {1, 3, 5, 7, 9, 11}에서, 8 이상인 값이 처음 나오는 위치를 구하는 과정: 
		1. 시작 위치= 1, 끝 위치= 6으로 설정한다.
		2. 시작 위치 1과 끝 위치 6의 중간 위치인 3((1+6) / 2)번째 값을 8과 비교한다.
		3. 5는 8보다 작으므로 시작 위치를 3 다음인 4로 설정한다.
		4. 시작 위치 4와 끝 위치 6의 중간 위치인 5번째 값을 8과 비교한다.
		5. 9는 8보다 크다. 이때에는 이분 탐색과 달리, 끝 위치를 중간 위치인 5로 설정한다.
			- 왜냐하면, 8 이상인 값이 처음 나오는 위치를 구하는 것이므로, 9가 Lower Bound가 될 수도 있다. 따라서 끝 값까지 포함한다.
		6. 시작 위치=4, 끝 위치=5이므로 중간 위치인 4번째 값을 8과 비교한다.
		7. 7은 8보다 작다. 따라서 시작 위치를 중간 위치+1 = 5로 설정한다.
		8. 시작 위치 = 끝 위치 = 5이므로 5번째 값인 9가 Lower Bound가 된다.
