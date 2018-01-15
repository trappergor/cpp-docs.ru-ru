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
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 387bd9733ad591f45ef206be8856d4dd4edd464d
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-rotate-images-with-the-net-framework"></a>Практическое руководство. Поворот изображений с помощью платформы .NET Framework
В следующем примере кода показано использование <xref:System.Drawing.Image?displayProperty=fullName> класс, чтобы загрузить изображения с диска, повернуть на 90 градусов и сохраните его в качестве нового JPG-файла.  
  
> [!NOTE]
>  GDI + входит в состав Windows XP и доступен в виде распространяемого пакета для 6 (SP2) для Windows NT 4.0, Windows 2000, Windows 98 и Windows Millennium Edition. Загрузке последнего распространяемого пакета см. в разделе [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232). 
  
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