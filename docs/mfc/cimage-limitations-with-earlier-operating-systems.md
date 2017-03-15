---
title: "Ограничения CImage в ранних версиях операционных систем | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImage - класс, ограничения"
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ограничения CImage в ранних версиях операционных систем
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Многие функции `CImage` работают только с более новыми версиями Windows: Windows 95\/98 или NT Windows 4.0 или Windows 2000.  В этом разделе описываются ограничения версии некоторых методов.  
  
 [CImage::PlgBlt](../Topic/CImage::PlgBlt.md) [CImage::MaskBlt](../Topic/CImage::MaskBlt.md) и работать только с NT Windows 4.0 или более поздней версии.  Они не могут использоваться в приложениях, в Windows 95\/98 или более поздней версии.  
  
 [CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md) [CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md) и работать только с Windows 2000 или более поздней версии и Windows 98 или более поздней версии, поскольку необходимо связать с msimg32.lib для использования этих методов. \(Эта библиотека доступна только приложениям, запущенным Windows 2000 или более поздней версии и Windows 98 или более поздней версии\).  
  
 Можно включить `AlphaBlend` и `TransparentBlt` приложения, выполняющиеся в Windows 95 или Windows 4.0 NT только в том случае, если эти методы никогда не получают которые.  Если приложение включает эти методы, и оно должно выполняться в предыдущих версиях операционных систем, необходимо использовать [\/delayload](../build/reference/delayload-delay-load-import.md) компоновщика для загрузки с задержкой. msimg32.lib.  Если приложение не вызывает один из этих методов при выполнении NT в Windows 4.0 или Windows 95, он не пытается загрузить msimg32.lib.  Можно проверить ли поддержка прозрачности доступна в метод `CImage::IsTransparencySupported`.  
  
## Пример  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/CPP/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 Чтобы компилировать приложение, которое вызывает эти методы, вставьте оператора \#define \_WIN32\_WINNT перед \#including все заголовки системы, что версия Windows равна или превышает 5.0:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/CPP/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 Если приложение не будет выполняться в операционной системе более ранней, чем Windows 2000 или Windows 98, можно связать непосредственно в msimg32.lib без использования **\/delayload**.  
  
 [CImage::Draw](../Topic/CImage::Draw.md) поведение по\-разному при использовании с Windows 2000 и Windows 98, а не делает с NT Windows 4.0 или Windows 95.  
  
 Если компилировать приложение с \_WIN32\_WINNT значение меньше значения 0x0500, **Рисование** будет работать, но не обрабатывает прозрачность автоматически в системах, Windows 2000 и Windows 98 и более поздних версиях.  
  
 Если компилировать приложение с \_WIN32\_WINNT установленного на 0x0500 или больше, **Рисование** обрабатывает прозрачность автоматически в системах, Windows 2000 или Windows 98 и более поздних версиях.  Она также будет работать, но без поддержки прозрачности, NT с Windows 4.0 и Windows 95; однако следует использовать **\/delayload** для загрузки с задержкой. msimg32.LIB, как описано выше в `AlphaBlend` и `TransparentBlt`.  
  
## См. также  
 [CImage Class](../atl-mfc-shared/reference/cimage-class.md)