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

## nx 주요기능 - Run Tasks

Syntax: nx <target name> <project name> <option overrides>

- nx는 단일 워크스페이스 혹은 전체 워크스페이스들에 대한 태스크 수행 명령어를 가지고 있습니다.
- 단일 워크스페이스 태스크 실행: nx build my-app
- 전체 워크스페이스 태스크 실행: nx run-many -t [script]

## nx 주요기능 - Cache Task Results

- 캐싱 기능 제공. 태스크 실행 명령어를 실행하면 여러방식의 설정 파일로부터 캐싱을 어떻게 하는지 체크합니다.
- nx.json / project.json / package.json 등을 이용해서 설정합니다.
- lerna와 비슷하다

## nx 주요기능 - Use Remote Caching
- Nx Cloud를 사용하면 원격 캐싱을 사용할 수 있습니다. - nx connect-to-nx-cloud
