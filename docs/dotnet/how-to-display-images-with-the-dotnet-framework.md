---
title: "Практическое руководство. Отображение изображений в платформе .NET Framework | Microsoft Docs"
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
  - "GDI+ [C++], отображение изображений"
  - "графика [C++], отображение изображений"
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Отображение изображений в платформе .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере обработчик событий OnPaint изменяется таким образом, чтобы извлекался указатель на объект <xref:System.Drawing.Graphics> главной формы.  Функция <xref:System.Windows.Forms.Form.OnPaint%2A> предназначена для приложений Windows Forms, чаще всего создаваемых с помощью мастера приложений Visual Studio.  
  
 Изображение представляется классом <xref:System.Drawing.Image>.  Графические данные загружаются из JPG\-файла с помощью метода <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>.  Перед рисованием изображения на форме ее размер изменяется в соответствии с размером изображения.  Рисование изображения выполняется с помощью метода <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName>.  
  
 Классы <xref:System.Drawing.Graphics> и <xref:System.Drawing.Image> принадлежат пространству имен <xref:System.Drawing?displayProperty=fullName>.  
  
> [!NOTE]
>  Библиотека GDI\+ включена в ОС Windows XP, а также доступна в виде распространяемого пакета для Windows NT 4.0 с пакетом обновлений 6 \(SP 6\), Windows 2000, Windows 98 и Windows Me.  Чтобы загрузить последний распространяемый пакет, посетите веб\-узел [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Дополнительные сведения см. в документации по пакету средств разработки SDK для GDI\+ в [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Пример  
  
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
  
## См. также  
 <xref:System.Drawing?displayProperty=fullName>   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)