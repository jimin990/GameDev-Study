## 1. PreLogin()
```
virtual void PreLogin(
    const FString& Options,
    const FString& Address,
    const FUniqueNetIdRepl& UniqueId,
    FString& ErrorMessage
) override;
```
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
## 3. PostLogin()
```
virtual void PostLogin(APlayerController* NewPlayer) override;
```
