# Skills

跨设备同步的 ZCode Skills 集合。每个 skill 是一个独立 git 子模块（submodule），可单独跟踪和推送。

## 包含的 Skills

| Skill | 子模块 Remote | 来源 |
|:---|:---|:---|
| seedance2.0-prompt-skill | Emptytao/seedance2.0-prompt-skill | 自建 |
| seedance-20 | Emptytao/seedance-2.0 | Fork from Emily2040/seedance-2.0 |
| short-drama | Emptytao/short-drama | Fork from 0xsline/short-drama |
| all-asset-master-v3 | Emptytao/all-asset-master-v3 | 自建 |
| vibe-image | Emptytao/vibe-image | 自建 |

## 安装（新设备）

```bash
# 克隆主仓库（自动初始化所有子模块）
git clone --recurse-submodules https://github.com/Emptytao/skills.git ~/.agents

# 可选：在 ~/.zcode/skills/ 创建符号链接（.zcode 优先级更高）
ln -s ~/.agents/skills/seedance2.0-prompt-skill ~/.zcode/skills/seedance2.0-prompt-skill
ln -s ~/.agents/skills/short-drama ~/.zcode/skills/short-drama
```

## 更新子模块

```bash
cd ~/.agents

# 拉取所有子模块的最新更新
git submodule update --remote --merge

# 提交子模块指针更新
git add . && git commit -m "chore: 更新子模块指针"
git push
```

## 在子模块内独立工作

```bash
cd ~/.agents/skills/seedance2.0-prompt-skill

# 正常修改、提交、推送（独立于主仓库）
git add -A && git commit -m "feat: xxx" && git push

# 回到主仓库更新指针
cd ~/.agents
git add skills/seedance2.0-prompt-skill
git commit -m "chore: 更新 seedance2.0-prompt-skill 指针"
git push
```
