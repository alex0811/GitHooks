# GitHooks

## Commit 规范

Commit 提交规范，是一种对代码提交描述的轻量约束。通过一些简单的格式来建立明确的提交记录，可以更好的对提交历史进行追溯，了解提交当时的背景与修改的目的。

**需要注意的是**，commit 中如果包含了不符合规范的信息，将会被拒绝提交。

> ERROR: Illegal commit submission format, please use the correct format:
>
> feat: add comments
>
> fix: handle events on blur (close #28)
>
> The full specification of the Gaoding Commit Message Format can be found at [Commit 规范](https://github.com/alex0811/GitHooks)

提交规范如下（参考 [Angular](https://github.com/angular/angular/blob/master/.gitmessage) ）：

```
<Type 提交类型>(<Scope 可选的作用范围>): <Subject 描述> 
<Body 可选的正文>
```

## Type

类型必须是以下其中一种：

- feat: 新功能、新特性
- fix: 修复 Bug，可以是 QA 提的 bug，也可以是自测发现的 bug
- docs: 仅文档修改
- style: 不影响代码功能的修改（如空格、格式化、补充分号等等）
- refactor: 代码重构（重构，在不影响代码内部行为、功能下的代码修改）
- perf: 更改代码，以提高性能（在不影响代码内部行为的前提下，对程序性能进行优化）
- test: 新增或修正单元测试
- build: 影响项目构建或依赖项修改
- chore: 其他修改（不在上述类型中的修改，如代码合并或者解决冲突）

举个例子，当我们完成了特性代码编写，我们可以通过以下命令提交 commit

```shell
git commit -m "feat: 添加了 xx 功能"
```

合并冲突时：

```shell
git commit -m "chore: 合并主分支，解决冲突"
```

## Scope

作用范围 Scope（可选）可以表示代码影响的范围。比如编译器、元素注入器等等。

## Subject

Subject 可以填写 Commit 的描述：

- 推荐使用现在时态，例如：使用 change 而不是 changed 或者 changes
- 不必首字母大写
- 不必结尾处使用句号或者句点

## Body

Commit 的具体修改内容（可选），可以多行显示。

当我们想对新特性 xxx 的提交信息补充更详细的内容时，参考 Git 的 [Commit 文档](https://git-scm.com/docs/git-commit)，我们可以使用多个 -m 符号表示多段文本：

```shell
git commit -m "feat: 添加了录音功能" -m "具体需求文档见 xxxx"
```