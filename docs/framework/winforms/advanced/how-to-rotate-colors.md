---
title: 如何：旋转颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175534"
---
# <a name="how-to-rotate-colors"></a>如何：旋转颜色
四维颜色空间中的旋转很难直观显示。 我们可以轻松地实现旋转同意接受保持一个固定的颜色组件的可视化效果。 假设我们同意将 alpha 分量固定在 1 （完全不透明）。 然后我们可以直观显示三维颜色空间具有红色、 绿色和蓝色的轴，如下图中所示。  
  
 ![显示具有红色、 绿色和蓝色轴旋转的图例。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 一种颜色可视为在三维空间中点。 例如，空间中的点 （1，0，0） 表示的颜色为红色，并在空间中的点 （0、 1、 0） 表示绿色。  
  
 下图通过红-绿平面中的 60 度的角度显示旋转的颜色 （1，0，0） 意味着什么。 在平面平行于红-绿平面旋转可以看作围绕蓝色轴的旋转。  
  
 ![显示有关蓝色轴旋转的图例。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 下图显示了如何初始化颜色矩阵执行三个坐标轴 （红色、 绿色、 蓝色） 的每个旋转：  
  
 ![初始化一个颜色矩阵以执行有关三个轴的旋转。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>示例  
 下面的示例将是一种颜色 （1，0，0.6） 和顺蓝色轴旋转 60 度的映像。 中对红-绿平面平行的平面上旋转的角度扫出。  
  
 下图显示在左侧和右侧的颜色旋转图像的原始图像：  
  
 ![显示原始图像和颜色旋转图像的图例。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 下图显示了执行下面的代码中的颜色旋转的可视化效果：
  
 ![显示颜色旋转的可视化效果的图例。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。 替换为`RotationInput.bmp`与图像文件名称和你的系统上有效的路径。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
