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
현재 게임/맵에 대한 초기 설정하는 함수입니다.
<br/><br/>
이 시점에 아직 플레이어, 즉 Controller는 없을 수 있습니다.

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
이 시점부터 GameState를 안전하게 호출할 수 있습니다.
<br/><br/>
GameMode도 Actor로써 이 후 InitializeComponent(), PostInitializeComponents()가 동작합니다.

## 6. StartPlay()
```
virtual void StartPlay() override
```
게임모드가 게임 시작을 트리거하면, GameState가 World에 BeginPlay를 요청합니다.
<br/><br/>
그러면 World는 World에 존재하는 모든 액터에게 BeginPlay를 브로드캐스트합니다.

## 7. BeginPlay()
```
virtual void BeginPlay() override;
```
