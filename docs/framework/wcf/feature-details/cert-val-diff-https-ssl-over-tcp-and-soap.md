---
title: HTTPS、通过 TCP 的 SSL 与 SOAP 安全之间的证书验证差异
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
ms.openlocfilehash: 0ab343da821e8994ac3a652bfc55db261d5e48f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089479"
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a>HTTPS、通过 TCP 的 SSL 与 SOAP 安全之间的证书验证差异
您可以使用证书在 Windows Communication Foundation (WCF) 消息层 (SOAP) 安全传输层安全性 (TLS) 除了通过 HTTP (HTTPS) 或 TCP。 本主题介绍此类证书的验证方式的差异。  
  
## <a name="validation-of-https-client-certificates"></a>验证 HTTPS 客户端证书  
 当使用 HTTPS 在客户端和服务间通信时，客户端用于向服务进行身份验证的证书必须支持链信任。 也就是说，它必须链至受信任的根证书颁发机构。 否则，HTTP 层引发<xref:System.Net.WebException>并显示消息"远程服务器返回了错误：(403) 禁止。" WCF 将作为此异常显示<xref:System.ServiceModel.Security.MessageSecurityException>。  
  
## <a name="validation-of-https-service-certificates"></a>验证 HTTPS 服务证书  
 当使用 HTTPS 在客户端和服务间通信时，服务器身份验证使用的证书默认情况下必须支持链信任。 也就是说，它必须链至受信任的根证书颁发机构。 不会执行任何在线检查来查看证书是否已吊销。 可以通过注册 <xref:System.Net.Security.RemoteCertificateValidationCallback> 回调来重写此行为，如以下代码所示。  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)] 
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 其中，`ValidateServerCertificate` 的签名如下：  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 实现 `ValidateServerCertificate` 可以执行客户端应用程序开发人员认为在验证服务证书时有必要进行的任何检查。  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a>验证通过 TCP 的 SSL 或 SOAP 安全中的客户端证书  
 使用通过 TCP 的安全套接字层 (SSL) 或消息 (SOAP) 安全时，根据 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 属性值验证客户端证书。 该属性设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 值之一。 根据 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 属性值的值来执行吊销检查。 该属性设置为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 值之一。  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a>验证通过 TCP 的 SSL 和 SOAP 安全中的服务证书  
 使用通过 TCP 的 SSL 或 (SOAP) 消息安全时，根据 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 属性值来验证服务证书。 该属性设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 值之一。  
  
 根据 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 属性值的值来执行吊销检查。 该属性设置为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 值之一。  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.Security.RemoteCertificateValidationCallback>
- [使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
