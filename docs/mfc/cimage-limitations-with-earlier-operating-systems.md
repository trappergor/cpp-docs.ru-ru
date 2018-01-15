---
title: "Ограничения CImage в ранних версиях операционных систем | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImage
dev_langs: C++
helpviewer_keywords: CImage class [MFC], limitations
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27046704975bf8f5e28f12acbfa72e860660fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-limitations-with-earlier-operating-systems"></a>Ограничения CImage в ранних версиях операционных систем
Многие `CImage` функции работают только с более новых версиях Windows: Windows 95/98 или Windows NT 4.0 или Windows 2000. В этой статье описываются ограничения версии из определенных методов.  
  
 [CImage::PlgBlt](../atl-mfc-shared/reference/cimage-class.md#plgblt) и [CImage::MaskBlt](../atl-mfc-shared/reference/cimage-class.md#maskblt) работают только в Windows NT 4.0 или более поздней версии. Они не будут работать в приложения, работающие в Windows 95/98 или более поздней версии.  
  
 [CImage::AlphaBlend](../atl-mfc-shared/reference/cimage-class.md#alphablend) и [CImage::TransparentBlt](../atl-mfc-shared/reference/cimage-class.md#transparentblt) работы с только Windows 2000 или более поздней версии и Windows 98 или более поздней версии, поскольку необходимо связать с msimg32.lib для использования этих методов. (Эта библиотека является доступной только для приложений под управлением Windows 2000 или более поздней версии и Windows 98 или более поздней версии).  
  
 Можно включить `AlphaBlend` и `TransparentBlt` в приложении, которое выполняется в Windows 95 или Windows NT 4.0, только в том случае, если эти методы не вызываются. Если приложение включает эти методы, а программа должна выполняться в более ранних операционных систем, необходимо использовать компоновщика [/DELAYLOAD](../build/reference/delayload-delay-load-import.md) загрузить msimg32.lib с задержкой. До тех пор, пока приложение не вызывает один из этих методов во время выполнения в группе Windows NT 4.0 или Windows 95, он не будет пытаться загрузить msimg32.lib. Можно проверить, является ли поддержки прозрачности будет доступно при использовании `CImage::IsTransparencySupported` метода.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 Для компиляции приложения, который вызывает эти методы, вставьте #define _WIN32_WINNT инструкцию перед #including каких-либо заголовков системы, указывающее, что версии Windows, равно или больше, чем 5.0:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 Если приложения не требуется для выполнения в операционной системе более ранней, чем Windows 2000 или Windows 98, можно связать непосредственно msimg32.lib без использования **/DELAYLOAD**.  
  
 [CImage::Draw](../atl-mfc-shared/reference/cimage-class.md#draw) ведет себя по-разному, при использовании с Windows 2000 и Windows 98, чем с Windows NT 4.0 или Windows 95.  
  
 При компиляции приложения с набором _WIN32_WINNT значение меньше 0x0500, **нарисовать** будет работать, но он не будет обрабатывать прозрачности автоматически в системах под управлением Windows 2000 и Windows 98 и более поздних версий.  
  
 При компиляции в приложение с _WIN32_WINNT значение 0x0500 или более поздней версии **нарисовать** обрабатывающий прозрачности автоматически в системах под управлением Windows 2000 или Windows 98 и более поздних версий. Оно также будет работать, но без поддержки прозрачности, с Windows NT 4.0 и Windows 95; Тем не менее, необходимо использовать **/DELAYLOAD** загрузить msimg32 с задержкой. LIB, как описано выше для `AlphaBlend` и `TransparentBlt`.  
  
## <a name="see-also"></a>См. также  
 [Класс CImage](../atl-mfc-shared/reference/cimage-class.md)
