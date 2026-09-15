# GameMode 생명주기와 함수 호출 순서를 알아보자.

## 1. 맵 로드

## 2. GameMode Constructor

## 3. InitGame()
```
virtual void InitGame(
    const FString& MapName,
    const FString& Options,
    FString& ErrorMessage
) override;
```
현재 게임/맵에 대한 초기 설정하는 함수

## 4. PreInitializeComponents()
```
virtual void PreInitializeComponents() override;
```
AActor 생명주기 함수로써, 게임모드에서는 이 시점에 InitGameState()를 호출합니다.

## 5. InitGameState()
```
virtual void InitGameState() override;
```
GameState를 초기화하는 GameMode 함수입니다.
<br/><br/>
GameMode도 Actor로써 이 후 InitializeComponent(), PostInitializeComponents()가 동작합니다.

## 6. StartPlay()
```
virtual void StartPlay() override
```
게임모드가 게임 시작을 트리거하고, World가 액터들의 Beginplay를 실행합니다.

## 7. BeginPlay()
```
virtual void BeginPlay() override;
```
