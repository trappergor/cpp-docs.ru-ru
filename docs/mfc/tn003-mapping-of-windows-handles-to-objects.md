---
title: 'TN003: Сопоставление Windows дескрипторов к объектам'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: e7844398ebaf5a8fdf8c56ab18b33d8c7717d1ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306383"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Сопоставление Windows дескрипторов к объектам

Эта заметка описывает MFC подпрограммы, которые поддерживает сопоставление Windows объекта дескрипторы для объектов C++.

## <a name="the-problem"></a>Проблема

Объекты Windows обычно представлены различные [ОБРАБАТЫВАТЬ](/windows/desktop/WinProg/windows-data-types) объектов классов MFC wrap маркеры объекта Windows с объектами C++. Дескриптор функции библиотеки классов MFC-оболочки позволяют найти объект C++, который является оболочкой Windows объект, имеющий определенного дескриптора. Тем не менее иногда объект не имеет объект-оболочку C++, и в это время система создает временный объект в качестве программы-оболочки C++.

Ниже приведены объекты Windows, использующие дескриптор карты.

- HWND ([CWnd](../mfc/reference/cwnd-class.md) и `CWnd`-производные классы)

- HDC ([CDC](../mfc/reference/cdc-class.md) и `CDC`-производные классы)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH (`CGdiObject`)

- HFONT (`CGdiObject`)

- HBITMAP (`CGdiObject`)

- HPALETTE (`CGdiObject`)

- HRGN (`CGdiObject`)

- HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- СОКЕТ ([CSocket](../mfc/reference/csocket-class.md))

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

Это делает запись в постоянное сопоставление связывание *myWnd* и *hWnd*. Вызов `CWnd::FromHandle(hWnd)` теперь возвращает указатель на *myWnd*. При *myWnd* будет удален, деструктор будет автоматически уничтожена *hWnd* путем вызова Windows [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow) функции. Если это нежелательно, *hWnd* необходимо отсоединить от *myWnd* перед *myWnd* уничтожении (обычно в том случае, при выходе из область, в которой *myWnd*был определен). `Detach` Метод делает следующее.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>Дополнительные сведения о временных объектов

Временные объекты создаются каждый раз, когда `FromHandle` Получает дескриптор, который еще не содержит объект-оболочку. Отсоединить от их дескриптора и удалить эти временные объекты `DeleteTempMap` функции. По умолчанию [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) автоматически вызывает `DeleteTempMap` для каждого класса, который поддерживает сопоставления временный дескриптор. Это означает, что нельзя предполагать, что указатель на временный объект будет допустимым за точкой выхода из функции которой был получен указатель.

## <a name="wrapper-objects-and-multiple-threads"></a>Объекты-оболочки и нескольких потоков

Временные и постоянные объекты обслуживаются на основе отдельного потока. То есть один поток не может получить доступ к объекты-оболочки C++, другой поток, даже если он является временным или постоянным.

Чтобы передать эти объекты из одного потока в другой, всегда отправлять их как свою внутреннюю `HANDLE` типа. Передавая объект-оболочку C++ из одного потока в другой часто привести к непредвиденным результатам.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
