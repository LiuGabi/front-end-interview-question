## <a name='clutter-quesition'>clutter 问题</a>

1. 图片下载和图片保存（包含base64位的图片保存）【针对手机浏览器】?
    1.  图片下载：`<a href="img.png" target="_blank" download="aaa.png">Download Pic</a>` [download 标志下载];
    2.  图片base64下载：按照1的方式，base64位的下载目前桌面浏览器尚可支持，mobile 浏览器则视为不支持的格式;
    3.  图片保存：mobile 浏览器长按图片可以唤起浏览器的保存功能; 
    4.  图片base64保存：支持3;

2. 淘宝镜像
    1.  设置：`npm config set registry https://registry.npm.taobao.org`, `npm config set disturl https://npm.taobao.org/dist`;
    2.  编辑删除: `npm config edit`;
    3.  命令删除: `npm config delete registry`, `npm config delete disturl`;
