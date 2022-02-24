```
        useEffect(()=> {
            
        });
```

컴포넌트가 mount 되었을때

컴포넌트가 update 될때

특정 코드를 실행할 수 있음



컴포넌트가 사라질 때 코드를 실행시킬 수도 있음

```
        useEffect(()=> {
            
            return ()=> {}
        });
```



useEffect는 적은 순서대로 실행된다.

```
        useEffect(()=> {    // 1번
            
            return ()=> {}
        });
        useEffect(()=> {   // 2번
            
            return ()=> {}
        });
```

