---
title: "Как: отображение изображений в платформе .NET Framework | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f50659832e04c3b8938c50bedc47b3ac770a52eb
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-display-images-with-the-net-framework"></a>Практическое руководство. Отображение изображений в платформе .NET Framework
В следующем примере кода обработчик событий OnPaint для получения указателя изменяется <xref:System.Drawing.Graphics> объект главной формы. <xref:System.Windows.Forms.Form.OnPaint%2A> Функция предназначена для приложения Windows Forms, скорее всего, созданные с использованием мастера приложений Visual Studio.  
  
 Изображение представляется <xref:System.Drawing.Image> класса. Графические данные загружаются из файла .jpg с помощью <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> метод. Перед рисованием изображения в форму, размер формы изменяется в соответствии с изображением. Рисование изображения выполняется с <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> метод.  
  
 <xref:System.Drawing.Graphics> И <xref:System.Drawing.Image> классы находятся в <xref:System.Drawing?displayProperty=fullName> пространства имен.  
  
## <a name="example"></a>Пример  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
protected:  
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override  
{  
    Graphics^ g = pe->Graphics;  
    Image^ image = Image::FromFile("SampleImage.jpg");  
    Form::ClientSize = image->Size;  
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );  
}  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing?displayProperty=fullName>   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)