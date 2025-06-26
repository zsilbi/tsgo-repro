### Reproduction steps

Install depencencies:

```bash
pnpm i
```

Run `tsgo`:

```bash
pnpm tsgo
```

### Stack trace

```bash
panic: runtime error: invalid memory address or nil pointer dereference
[signal SIGSEGV: segmentation violation code=0x1 addr=0x100 pc=0x7917cb]

goroutine 85 [running]:
github.com/microsoft/typescript-go/internal/checker.(*Checker).getBaseTypes(0xc001035908, 0xc000f8a9a0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:18245 +0x2b
github.com/microsoft/typescript-go/internal/checker.(*Checker).typeHasProtectedAccessibleBase(0xc001035908, 0xc00019e8c0, 0xc0001da05f?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8363 +0x25
github.com/microsoft/typescript-go/internal/checker.(*Checker).typeHasProtectedAccessibleBase(0xc001035908, 0xc00019e8c0, 0xc000f1b8e8?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8389 +0xc5
github.com/microsoft/typescript-go/internal/checker.(*Checker).isConstructorAccessible(0xc001035908, 0xc000150af0, 0x1?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8347 +0x225
github.com/microsoft/typescript-go/internal/checker.(*Checker).resolveNewExpression(0xc001035908, 0xc000150af0, 0x0, 0x0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8287 +0x145
github.com/microsoft/typescript-go/internal/checker.(*Checker).resolveSignature(0xc001035f18?, 0xd10b60?, 0xc000150af0?, 0x7fbe4e?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8143 +0x3a
github.com/microsoft/typescript-go/internal/checker.(*Checker).getResolvedSignature(0xc001035908, 0xc000150af0, 0x0, 0x0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8113 +0xd8
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkCallExpression(0xc001035908, 0xc000150af0, 0x0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:8008 +0x4f
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkExpressionWorker(0xc001035908, 0x7f5890?, 0x1035908?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:7392 +0x325
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkExpressionEx(0xc001035908, 0xc000150af0, 0x0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:7178 +0x52
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkExpression(...)
        github.com/microsoft/typescript-go/internal/checker/checker.go:7171
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkExpressionStatement(0xc001035908, 0xc000173900)
        github.com/microsoft/typescript-go/internal/checker/checker.go:6951 +0x46
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElementWorker(0xc001035908, 0xc000173900)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2231 +0x29e
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElement(0xc001035908, 0x0?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2157 +0x4e
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElements(0xc001035908, {0xc0001349c8, 0x1, 0x598da7?})
        github.com/microsoft/typescript-go/internal/checker/checker.go:2148 +0x2d
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkBlock(0xc001035908, 0xc0001dc060)
        github.com/microsoft/typescript-go/internal/checker/checker.go:3590 +0xfc
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElementWorker(0xc001035908, 0xc0001dc060)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2227 +0x365
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElement(0xc001035908, 0xc0004eb0e8?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2157 +0x4e
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkFunctionOrMethodDeclaration(0xc001035908, 0xc0001252c0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:3258 +0x131
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkMethodDeclaration(0xc001035908, 0xc0001252c0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2623 +0x11b
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElementWorker(0xc001035908, 0xc0001252c0)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2183 +0xd9
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElement(0xc001035908, 0x46fc59?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2157 +0x4e
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElements(0xc001035908, {0xc0001349d0, 0x1, 0xc001035908?})
        github.com/microsoft/typescript-go/internal/checker/checker.go:2148 +0x2d
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkClassDeclaration(0xc001035908, 0xc00019c360)
        github.com/microsoft/typescript-go/internal/checker/checker.go:4075 +0x133
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElementWorker(0xc001035908, 0xc00019c360)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2263 +0x347
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElement(0xc001035908, 0xc0016044b0?)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2157 +0x4e
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceElements(0xc001035908, {0xc0001349d8, 0x3, 0xc00002cb10?})
        github.com/microsoft/typescript-go/internal/checker/checker.go:2148 +0x2d
github.com/microsoft/typescript-go/internal/checker.(*Checker).checkSourceFile(0xc001035908, {0xd0b760, 0x126a380}, 0xc0001818c8)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2120 +0x11c
github.com/microsoft/typescript-go/internal/checker.(*Checker).CheckSourceFile(0xc001035908, {0xd0b760, 0x126a380}, 0xc0001818c8)
        github.com/microsoft/typescript-go/internal/checker/checker.go:2109 +0x5c
github.com/microsoft/typescript-go/internal/compiler.(*Program).CheckSourceFiles.func1-range1(0x1?)
        github.com/microsoft/typescript-go/internal/compiler/program.go:273 +0x3e
github.com/microsoft/typescript-go/internal/compiler.(*checkerPool).Files.func1(0xc001604480)
        github.com/microsoft/typescript-go/internal/compiler/checkerpool.go:82 +0x88
github.com/microsoft/typescript-go/internal/compiler.(*Program).CheckSourceFiles.func1()
        github.com/microsoft/typescript-go/internal/compiler/program.go:272 +0xdb
github.com/microsoft/typescript-go/internal/core.(*parallelWorkGroup).Queue.func1()
        github.com/microsoft/typescript-go/internal/core/workgroup.go:39 +0x50
created by github.com/microsoft/typescript-go/internal/core.(*parallelWorkGroup).Queue in goroutine 1
        github.com/microsoft/typescript-go/internal/core/workgroup.go:37 +0x85

 ELIFECYCLE  Command failed with exit code 2.
```
