wezterm配置文件

路径 ～/.config/wezterm/wezterm.lua

配置文件：  #记得改背景图路径
```
local wezterm = require("wezterm")
local config = wezterm.config_builder()

-- 基本设置
config.automatically_reload_config = true
config.enable_tab_bar = false
config.window_close_confirmation = "NeverPrompt"
-- config.window_decorations = "RESIZE"
config.default_cursor_style = "SteadyBlock"

-- 字体设置：JetBrains Mono 加粗，大小17
-- config.font = wezterm.font("Menlo", { weight = "Bold", italic = true })
config.font = wezterm.font("JetBrains Mono", { weight = "Bold" })
config.font_size = 17

-- 背景图片设置（柔和）
config.window_background_image = "/Users/mikilin/Pictures/monterey.jpg"
config.window_background_image_hsb = {
    hue = 1.0,
    saturation = 0.84,
    brightness = 0.84,
}

config.window_background_opacity = 0.35  -- 背景半透明
config.background = {
    {
        source = { Color = "#000000" }, -- 黑色覆盖
        width = "100%",
        height = "100%",
        opacity = 0.21,
    }
}

-- 文字颜色设置为纯白
config.color_schemes = {
    ["CustomWhite"] = {
        foreground = "#FFFFFF",  -- 文字白色
        background = "#000000",  -- 背景可忽略，因为有图片
        cursor_bg = "#FFFFFF",
        cursor_fg = "#000000",
        cursor_border = "#FFFFFF",
        selection_bg = "#555555",
        selection_fg = "#FFFFFF",
        ansi = { "#000000", "#FF5555", "#50FA7B", "#F1FA8C", "#BD93F9", "#FF79C6", "#8BE9FD", "#BBBBBB" },
        brights = { "#555555", "#FF5555", "#50FA7B", "#F1FA8C", "#BD93F9", "#FF79C6", "#8BE9FD", "#FFFFFF" },
    }
}
config.color_scheme = "CustomWhite"

-- 窗口边缘
config.window_padding = {
    left = 21,
    right = 21,
    top = 21,
    bottom = 21,
}

return config
```