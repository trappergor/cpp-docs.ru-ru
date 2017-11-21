---
title: "Как: преобразование форматов файлов изображений с платформой .NET Framework | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eff94d00f92fe0a52162c986662209168974e072
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>Практическое руководство. Преобразование файлов изображений из одного формата в другой с помощью платформы .NET Framework
В следующем примере кода показано <xref:System.Drawing.Image?displayProperty=fullName> класса и <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> перечисление, используемое для преобразования и сохранения файлов изображений. Следующий код загружает изображение из JPG-файл и затем сохраняет его в форматах GIF и BMP.  
  
> [!NOTE]
>  GDI + входит в состав Windows XP, Windows Server 2003 и Windows Vista и доступен в виде распространяемого пакета для Windows 2000. Загрузке последнего распространяемого пакета см. в разделе [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232).   
  
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