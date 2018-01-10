---
title: "Как: Рисование фигур с платформой .NET Framework | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62579ca21ba4a4dcf89aea6ff717ce6c884073b3
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>Практическое руководство. Рисование фигур с помощью платформы .NET Framework
Следующий пример кода использует <xref:System.Drawing.Graphics> класса, чтобы изменить <xref:System.Windows.Forms.Form.OnPaint%2A> обработчик событий, чтобы получить указатель на <xref:System.Drawing.Graphics> объект главной формы. Затем этот указатель используется для задать цвет фона формы и рисования линии и дуги с помощью <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> и <xref:System.Drawing.Graphics.DrawArc%2A> методы.  
  
> [!NOTE]
>  GDI + входит в состав Windows XP и доступен в виде распространяемого пакета для 6 (SP2) для Windows NT 4.0, Windows 2000, Windows 98 и Windows Me. Загрузке последнего распространяемого пакета см. в разделе [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232). 
  
## <a name="example"></a>Пример  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Пространство имен System::Drawing](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)