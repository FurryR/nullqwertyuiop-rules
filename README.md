# 自定义规则

[@nullqwertyuiop](https://github.com/nullqwertyuiop) 手改的 Clash 规则，适用于大部分场合。

# clash-rules

这是适配 [clash-rules](https://github.com/FurryR/clash-rules) 的规则，如果没有请先去下载。

```javascript
{
  rules: [
    {
      type: 'url-test',
      url: new URL('http://www.gstatic.com/generate_204'),
      name: '♻️ 自动选择',
      interval: 300,
      tolerance: 50,
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/ProxyGFWlist.yaml',
      ),
      name: '🚀 节点选择',
      behavior: 'classical',
      proxy: ['♻️ 自动选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/Private.yaml',
      ),
      name: '🎯 全球直连',
      behavior: 'domain',
      proxy: ['DIRECT', 'REJECT'],
    },
    {
      type: 'select',
        rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/LocalAreaNetwork.yaml',
      ),
      name: '🎯 全球直连',
      behavior: 'classical',
      proxy: ['DIRECT', 'REJECT'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/PrivateTracker.yaml',
      ),
      name: '🎯 全球直连',
      behavior: 'classical',
      proxy: ['DIRECT', 'REJECT'],
    },
    {
      type: 'select',
      name: '🛑 全球拦截',
      proxy: ['REJECT', 'DIRECT'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/ProxyMedia.yaml',
      ),
      name: '🌍 国外媒体',
      behavior: 'classical',
      proxy: ['🚀 节点选择', '🎯 全球直连', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/Telegram.yaml',
      ),
      name: '📲 电报信息',
      behavior: 'classical',
      proxy: ['🚀 节点选择', '🎯 全球直连', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/Microsoft.yaml',
      ),
      name: 'Ⓜ️ 微软服务',
      behavior: 'classical',
      proxy: ['🎯 全球直连', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/Apple.yaml',
      ),
      name: '🍎 苹果服务',
      proxy: ['🎯 全球直连', '🚀 节点选择', '|'],
      behavior: 'classical',
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/GoogleFCM.yaml',
      ),
      name: '📢 谷歌推送',
      proxy: ['🚀 节点选择', '🎯 全球直连', '|'],
      behavior: 'classical',
    },
    {
      type: 'select',
      rule: 'DOMAIN,openai.com',
      name: '💡 OpenAI',
      proxy: ['🚀 节点选择', '🎯 全球直连', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/IPAttribution.yaml',
      ),
      name: '🌐 IP 属地',
      behavior: 'classical',
      proxy: ['🚀 节点选择', '🎯 全球直连', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/CNcidr.yaml',
      ),
      name: '🇨🇳 中国大陆',
      behavior: 'ipcidr',
      proxy: ['🎯 全球直连', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/BanProgramAD.yaml',
      ),
      name: '🍃 应用净化',
      behavior: 'classical',
      proxy: ['🛑 全球拦截', '🎯 全球直连', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/BanAD.yaml',
      ),
      name: '🚫 广告跟踪',
      behavior: 'classical',
      proxy: ['🛑 全球拦截', '🎯 全球直连', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/BanEasyList.yaml',
      ),
      name: '🚫 广告跟踪',
      behavior: 'classical',
      proxy: ['🛑 全球拦截', '🎯 全球直连', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/BanEasyPrivacy.yaml',
      ),
      name: '🚫 广告跟踪',
      behavior: 'classical',
      proxy: ['🛑 全球拦截', '🎯 全球直连', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: new URL(
        'https://raw.githubusercontent.com/FurryR/nullqwertyuiop-rules/main/rule/Applications.yaml',
      ),
      name: '🔈 软件绕过',
      behavior: 'classical',
      proxy: ['🎯 全球直连', '🛑 全球拦截', '🚀 节点选择', '|'],
    },
    {
      type: 'select',
      rule: 'MATCH',
      name: '🐟 漏网之鱼',
      proxy: ['🚀 节点选择', '🎯 全球直连', '🛑 全球拦截', '|'],
    },
  ],
  override: ['proxy-groups', 'rule-providers', 'rules'],
  // override 可加可不加，适用于提供商已经提供规则的场合
  // 如果出现吞代理的情况，请注释掉 override 行
}
```
