# 멀티에서 GameMode 접속 흐름과 함수 호출 순서

## 1. PreLogin()
```
virtual void PreLogin(
    const FString& Options,
    const FString& Address,
    const FUniqueNetIdRepl& UniqueId,
    FString& ErrorMessage
) override;
```
플레이어의 접속 허가를 담당합니다.
<br/><br/>
이 경우 매개변수로 들어온, ErrorMessage에 값을 넣는다면, 접속을 거부하게 됩니다.
<br/><br/>
Seamless Traval을 사용하는 경우 Controller를 재생성하지 않기 때문에 호출되지 않습니다.
<br/><br/>
## 2. Login()
```
virtual APlayerController* Login(
    UPlayer* NewPlayer,
    ENetRole InRemoteRole,
    const FString& Portal,
    const FString& Options,
    const FUniqueNetIdRepl& UniqueId,
    FString& ErrorMessage
) override;
```
접속한 플레이어의 컨트롤러 생성합니다.
<br/><br/>
마찬가지로 Seamless Traval을 사용하는 경우 Controller를 재생성하지 않기 때문에 호출되지 않습니다.
<br/><br/>
## 3. PostLogin()
```
virtual void PostLogin(APlayerController* NewPlayer) override;
```
로그인 완료 후 게임 참가 처리를 담당합니다.
