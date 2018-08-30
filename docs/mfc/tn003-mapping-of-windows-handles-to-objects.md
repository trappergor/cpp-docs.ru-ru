---
title: 'TN003: Сопоставление Windows дескрипторов к объектам | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mapping
dev_langs:
- C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7dbd74a8f216efb64d220747155a619d2084b3b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211766"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003. Сопоставление дескрипторов Windows с объектами
Эта заметка описывает MFC подпрограммы, которые поддерживает сопоставление Windows объекта дескрипторы для объектов C++.  
  
## <a name="the-problem"></a>Проблема  
 Объекты Windows обычно представлены различные [ОБРАБАТЫВАТЬ](/windows/desktop/WinProg/windows-data-types) объектов классов MFC wrap маркеры объекта Windows с объектами C++. Дескриптор функции библиотеки классов MFC-оболочки позволяют найти объект C++, который является оболочкой Windows объект, имеющий определенного дескриптора. Тем не менее иногда объект не имеет объект-оболочку C++, и в это время система создает временный объект в качестве программы-оболочки C++.  
  
 Ниже приведены объекты Windows, использующие дескриптор карты.  
  
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
  
 Учитывая дескриптор в любой из этих объектов, можно найти объект MFC, который окружает дескриптор, вызвав статический метод `FromHandle`. Например, если вызывается HWND *hWnd*, возвращает указатель на следующую строку `CWnd` , который служит оболочкой *hWnd*:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Если *hWnd* не поддерживает объект определенного-оболочку, временный `CWnd` создания программы-оболочки для *hWnd*. Это дает возможность получить допустимый объект C++ из любого дескриптора.  
  
 Получив объект-оболочку, можно получить его дескриптор из переменной открытого члена класса-оболочки. В случае использования `CWnd`, *m_hWnd* содержит HWND для этого объекта.  
  
## <a name="attaching-handles-to-mfc-objects"></a>Присоединение дескрипторов к объектам MFC  
 Получив объект оболочки только что созданный дескриптор и дескриптор в объект Windows, можно связать два путем вызова `Attach` работать как в следующем примере:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 Это делает запись в постоянное сопоставление связывание *myWnd* и *hWnd*. Вызов `CWnd::FromHandle(hWnd)` теперь возвращает указатель на *myWnd*. При *myWnd* будет удален, деструктор будет автоматически уничтожена *hWnd* путем вызова Windows [DestroyWindow](https://msdn.microsoft.com/library/windows/desktop/ms632682) функции. Если это нежелательно, *hWnd* необходимо отсоединить от *myWnd* перед *myWnd* уничтожении (обычно в том случае, при выходе из область, в которой *myWnd*был определен). `Detach` Метод делает следующее.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>Дополнительные сведения о временных объектов  
 Временные объекты создаются каждый раз, когда `FromHandle` Получает дескриптор, который еще не содержит объект-оболочку. Отсоединить от их дескриптора и удалить эти временные объекты `DeleteTempMap` функции. По умолчанию [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) автоматически вызывает `DeleteTempMap` для каждого класса, который поддерживает сопоставления временный дескриптор. Это означает, что нельзя предполагать, что указатель на временный объект будет допустимым за точкой выхода из функции которой был получен указатель.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>Объекты-оболочки и нескольких потоков  
 Временные и постоянные объекты обслуживаются на основе отдельного потока. То есть один поток не может получить доступ к объекты-оболочки C++, другой поток, даже если он является временным или постоянным.  
  
 Чтобы передать эти объекты из одного потока в другой, всегда отправлять их как свою внутреннюю `HANDLE` типа. Передавая объект-оболочку C++ из одного потока в другой часто привести к непредвиденным результатам.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

