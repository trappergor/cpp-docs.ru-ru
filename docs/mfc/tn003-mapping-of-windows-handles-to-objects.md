---
title: "TN003: Сопоставление дескрипторов Windows к объектам | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mapping
dev_langs: C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e53b2569b0da6bfa63c94adb7bb163e5bcd6b7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003. Сопоставление дескрипторов Windows с объектами
Эта заметка описывает MFC подпрограммы, которые поддерживает сопоставление Windows объекта дескрипторы объектов C++.  
  
## <a name="the-problem"></a>Проблема  
 Windows объекты обычно представлены различные [ОБРАБОТКИ](http://msdn.microsoft.com/library/windows/desktop/aa383751) объектов классов MFC wrap Windows дескрипторы объектов с объектами C++. Дескриптор упаковки функции библиотеки классов MFC используются для поиска объекта C++, — это заключение объект Windows с определенного дескриптора. Тем не менее иногда объект не имеет объект-оболочка C++, а в это время система создаст временный объект в качестве оболочки для C++.  
  
 Объекты Windows, использовать дескриптор карты, следующим образом:  
  
-   HWND ([CWnd](../mfc/reference/cwnd-class.md) и `CWnd`-производные классы)  
  
-   HDC ([CDC](../mfc/reference/cdc-class.md) и `CDC`-производные классы)  
  
-   HMENU ([CMenu](../mfc/reference/cmenu-class.md))  
  
-   HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))  
  
-   HBRUSH (`CGdiObject`)  
  
-   HFONT (`CGdiObject`)  
  
-   HBITMAP (`CGdiObject`)  
  
-   HPALETTE (`CGdiObject`)  
  
-   HRGN (`CGdiObject`)  
  
-   HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))  
  
-   СОКЕТ ([CSocket](../mfc/reference/csocket-class.md))  
  
 Получает дескриптор на любой из этих объектов, можно найти объект MFC, который создает оболочку для дескриптора путем вызова статического метода `FromHandle`. Например, если вызывается HWND `hWnd`, возвращает указатель на следующую строку `CWnd` -оболочки `hWnd`:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Если `hWnd` не поддерживает объект конкретной оболочки временную `CWnd` создания программы-оболочки для `hWnd`. Это дает возможность получить допустимый объект C++ из любого дескриптора.  
  
 После того как вы это объект-оболочка, его дескриптор можно получить из переменной открытый член класса-оболочки. В случае использования `CWnd`, `m_hWnd` содержит HWND для этого объекта.  
  
## <a name="attaching-handles-to-mfc-objects"></a>Присоединение маркеры с объектами MFC  
 Получив объект оболочки дескриптор только что созданный и дескриптор объекта Windows, можно связать два путем вызова `Attach` работать как в следующем примере:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 Это делает запись в постоянное сопоставление связывание `myWnd` и `hWnd`. Вызов `CWnd::FromHandle(hWnd)` теперь возвращает указатель на `myWnd`. При `myWnd` будет удален, деструктор будет автоматически уничтожена `hWnd` путем вызова Windows [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) функции. Если это нежелательно, `hWnd` необходимо отсоединить от `myWnd` перед `myWnd` уничтожается (обычно в том случае, при выходе из области, с которой `myWnd` был определен). `Detach` Метод делает это.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>Дополнительные сведения о временных объектов  
 Временные объекты создаются каждый раз, когда `FromHandle` получает маркер, который еще не содержит объект-оболочка. Эти временные объекты отсоединяются от их дескриптор и удалить `DeleteTempMap` функции. По умолчанию [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) автоматически вызывает `DeleteTempMap` для каждого класса, который поддерживает сопоставления временный дескриптор. Это означает, что не может предположить, что указатель на временный объект будет действительна за точкой выхода из функции которой был получен указатель.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>Объекты-оболочки и несколько потоков  
 Временные и постоянные объекты сохраняются отдельно для каждого потока. То есть один поток не может получить доступ к объекты-оболочки C++ другого потока независимо от того, является ли он временным или постоянным.  
  
 Передать эти объекты из одного потока в другой, всегда отправлять их в их собственном `HANDLE` типа. Передача объект-оболочка C++ из одного потока в другой часто привести к непредвиденным результатам.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

