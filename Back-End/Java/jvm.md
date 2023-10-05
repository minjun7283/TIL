# JVM

JVM(Java Virtual Machine)이란 자바를 실행시키기 위한 가상 컴퓨터이다. 

java는 OS에 종속적이지 않다는 특징을 가지고 있다. OS에 종속받지 않고 실행되기 위해서는 OS 위에서 java를 실행시킬 무언가가 필요한데 이것이 JVM이다.  

java 코드는 CPU가 인식하지 못하여 기계어로 컴파일시켜 줘야한다. 따라서 기계어로 컴파일을 시켜줘야 하는데 우선 자바 컴파일러가 java 코드를 java bytecode로 변환해준다. 그리고 JVM이 java bytecode를 OS가 인식할 수 있는 기계어로 변환해준다.