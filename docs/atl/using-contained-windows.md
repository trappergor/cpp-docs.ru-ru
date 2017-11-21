---
title: "С помощью автономной Windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 08d263e07a828fb1b4d485fc6f80be68d52142dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="using-contained-windows"></a>С помощью автономной Windows
ATL реализует автономной windows с [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Содержащееся окно представляет окно, которая передает сообщения для объекта-контейнера вместо обработки их в свой собственный класс.  
  
> [!NOTE]
>  Необходимо унаследовать класс `CContainedWindowT` для использования автономных windows.  
  
 С помощью автономной windows можно либо суперкласса существующего класса Windows или подкласс существующему окну. Для создания окна, существующими Windows является суперклассом класса, сначала укажите имя существующего класса в конструкторе для `CContainedWindowT` объекта. Затем вызовите `CContainedWindowT::Create`. Подкласс существующему окну не требуется указать имя класса Windows (передать **NULL** в конструктор). Просто вызвать `CContainedWindowT::SubclassWindow` метод с дескриптором окна подкласса.  
  
 Обычно используется автономной windows как данные-члены класса контейнера. Контейнер не обязательно должно окно. Тем не менее, он должен быть производным от [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Содержащееся окно можно использовать схемы альтернативный сообщений для обработки сообщения. При наличии более одного содержащееся окно, следует объявить, что некоторые альтернативные схемы сообщений, соответствующие каждой в отдельном окне автономной.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример класса контейнера с двумя автономной windows:  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 Дополнительные сведения об автономной windows см. в разделе [SUBEDIT](../visual-cpp-samples.md) образца.  
  
## <a name="see-also"></a>См. также  
 [Классы окон](../atl/atl-window-classes.md)

