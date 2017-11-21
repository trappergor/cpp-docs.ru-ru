---
title: "Как: поворот изображений с .NET Framework | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], rotating images
- graphics [C++], rotating images
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b5b337186f67758d56dbc0bae06b6886f43f7435
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-rotate-images-with-the-net-framework"></a>Практическое руководство. Поворот изображений с помощью платформы .NET Framework
В следующем примере кода показано использование <xref:System.Drawing.Image?displayProperty=fullName> класс, чтобы загрузить изображения с диска, повернуть на 90 градусов и сохраните его в качестве нового JPG-файла.  
  
> [!NOTE]
>  GDI + входит в состав Windows XP и доступен в виде распространяемого пакета для 6 (SP2) для Windows NT 4.0, Windows 2000, Windows 98 и Windows Millennium Edition. Загрузке последнего распространяемого пакета см. в разделе [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232). 
  
## <a name="example"></a>Пример  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );  
   image->Save("SampleImage_rotated.jpg");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)