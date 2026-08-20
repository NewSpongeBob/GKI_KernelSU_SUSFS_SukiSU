# TODO

## 待实现

### CLI root 授权工具
- [ ] 内核侧：patch `dispatch.c` 将 `SET_APP_PROFILE` 权限从 `only_manager` 改为 `manager_or_root`
- [ ] 用户侧：写一个独立 C 程序 `ksu_grant`，通过 reboot syscall 获取 KSU fd，调用 `KSU_IOCTL_SET_APP_PROFILE` ioctl 授权
- [ ] 用法：`ksu_grant <package_name> <uid>` （需 root 执行）
- [ ] 注意：struct app_profile 需严格按 uapi/app_profile.h 定义对齐，否则 ioctl 会失败
