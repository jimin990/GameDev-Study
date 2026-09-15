GameMode 생명주기와 함수 호출 순서를 알아보자.

1. 맵 로드

2. GameMode Constructor

3.
```
virtual void InitGame(
    const FString& MapName,
    const FString& Options,
    FString& ErrorMessage
) override;
```
