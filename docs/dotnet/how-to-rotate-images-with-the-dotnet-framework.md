---
title: "Практическое руководство. Поворот изображений с помощью платформы .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GDI+ [C++], поворачивание изображений"
  - "графика [C++], поворачивание изображений"
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Поворот изображений с помощью платформы .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода показано использование класса <xref:System.Drawing.Image?displayProperty=fullName> для загрузки изображения с диска, поворота изображения на 90 градусов и сохранения его в качестве нового JPG\-файла.  
  
> [!NOTE]
>  GDI\+ включено в состав Windows XP и доступно в качестве распространяемого пакета для Windows NT 4.0 SP 6, Windows 2000, Windows 98 и Windows Millennium Edition.  Чтобы загрузить последний распространяемый пакет, посетите веб\-узел [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Дополнительные сведения см. в разделе [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Пример  
  
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
  
## См. также  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)