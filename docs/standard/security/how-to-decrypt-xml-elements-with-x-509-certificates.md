---
title: 如何：使用 X.509 证书解密 XML 元素
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 72e5f1e72d3ce7ec954d61216bbac2e0e1b5a428
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301199"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a>如何：使用 X.509 证书解密 XML 元素
可以使用 <xref:System.Security.Cryptography.Xml> 命名空间中的类对 XML 文档内的元素进行加密和解密。  XML 加密是交换或存储加密的 XML 数据的一种标准方式，使用后就无需担心数据被轻易读取。  有关 XML 加密标准的详细信息，请参阅万维网联合会 (W3C) 规范 XML 加密位于 <https://www.w3.org/TR/xmldsig-core/>。  
  
 此示例使用中所述的方法进行加密的 XML 元素进行解密：[如何：使用 X.509 证书加密 XML 元素](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)。  找到 <`EncryptedData`> 元素中，对元素进行解密，然后替换原始的纯文本 XML 元素的元素。  
  
 此过程中的代码示例将使用当前用户帐户的本地证书存储中的 X.509 证书来解密 XML 元素。  该示例使用<xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>方法来自动检索 X.509 证书和解密的会话密钥存储在 <`EncryptedKey`> 元素的 <`EncryptedData`> 元素。  然后，<xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 方法将自动使用会话密钥对 XML 元素进行解密。  
  
 此示例适用于以下情况：多个应用程序需要共享加密数据，或应用程序需要保存它各次运行之间的加密数据。  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a>用 X.509 证书解密 XML 元素  
  
1. 通过从磁盘加载 XML 文件来创建 <xref:System.Xml.XmlDocument> 对象。  <xref:System.Xml.XmlDocument> 对象包含要解密的 XML 元素。  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. 通过将 <xref:System.Xml.XmlDocument> 对象传递给构造函数，创建一个新的 <xref:System.Security.Cryptography.Xml.EncryptedXml> 对象。  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. 使用 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 方法解密 XML 文档。  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. 保存 <xref:System.Xml.XmlDocument> 对象。  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a>示例  
 此示例假定名为 `"test.xml"` 的文件与已编译程序存在于同一目录中。  它还假定 `"test.xml"` 包含 `"creditcard"` 元素。  可以将以下 XML 放在名为 `test.xml` 的文件，并将其用于以下示例。  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   若要编译此示例，需要包含对 `System.Security.dll` 的引用。  
  
-   包括以下命名空间：<xref:System.Xml>、<xref:System.Security.Cryptography> 和 <xref:System.Security.Cryptography.Xml>。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 此示例中使用的 X.509 证书仅用于测试目的。  应用程序应使用由受信任的证书颁发机构生成的 X.509 证书，或使用由 Microsoft Windows 证书服务器生成的证书。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Security.Cryptography.Xml>
- [如何：使用 X.509 证书加密 XML 元素](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)
