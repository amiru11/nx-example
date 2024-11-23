# nx-example
> 이 프로젝트는 Node.js v20.10.0, pnpm 9.14.2, Next.js 15.0.3을 사용하여 Nx 워크스페이스를 설정하고, Next.js 애플리케이션과 TypeScript 유틸리티 패키지를 통합하는 예제입니다.

## 사전 요구 사항
Node.js: v20.10.0
pnpm: 9.14.2
프로젝트 설정
프로젝트 디렉토리 생성 및 초기화

```(bash)
mkdir nx-example
cd nx-example
pnpm init
corepack enable
corepack prepare pnpm@9.14.2 --activate
```

## 워크스페이스 설정

pnpm-workspace.yaml 파일을 생성하고 다음 내용을 추가합니다:


```(yaml)
packages:
  - 'apps/*'
  - 'packages/*'
```

Next.js 애플리케이션 생성

디렉토리 생성 및 이동


```(bash)
mkdir -p apps/my-app
cd apps/my-app
```

## Next.js 애플리케이션 생성


```(bash)
pnpx create-next-app@latest
```
개발 서버 실행


```(bash)
pnpm --filter my-app dev
```
