---
title: "Как: преобразование форматов файлов изображений с платформой .NET Framework | Документы Microsoft"
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
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c40cef7c985df1d209e36f0d8a8e580106c3dc20
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>Практическое руководство. Преобразование файлов изображений из одного формата в другой с помощью платформы .NET Framework
В следующем примере кода показано <xref:System.Drawing.Image?displayProperty=fullName> класса и <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> перечисление, используемое для преобразования и сохранения файлов изображений. Следующий код загружает изображение из JPG-файл и затем сохраняет его в форматах GIF и BMP.  
  
## <a name="example"></a>Пример  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
using namespace System::Drawing::Imaging;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->Save("SampleImage.png", ImageFormat::Png);  
   image->Save("SampleImage.bmp", ImageFormat::Bmp);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing>   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)