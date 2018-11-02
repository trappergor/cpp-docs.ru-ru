---
title: Класс CMultiPageDHtmlDialog
ms.date: 11/04/2016
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 680c485241b7a377d1c6f0ec2785dbbade01ed3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443555"
---
# <a name="cmultipagedhtmldialog-class"></a>Класс CMultiPageDHtmlDialog

Многостраничное диалоговое окно последовательно отображает несколько HTML-страниц и обрабатывает события каждой страницы.

## <a name="syntax"></a>Синтаксис

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Создает объект диалогового окна DHTML многостраничной (мастер в стиле).|
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Уничтожает объект многостраничной DHTML-диалоговое окно.|

## <a name="remarks"></a>Примечания

— Это механизм [схема событий DHTML и URL-адрес](dhtml-event-maps.md), который содержит встроенные схемы событий для каждой страницы.

## <a name="example"></a>Пример

Этот многостраничное диалоговое окно предполагает три ресурса HTML, которые определяют простые функции в стиле мастера. Первая страница содержит **Далее** кнопки, второй **Prev** и **Далее** кнопки, а третий **Prev** кнопки. При нажатии одной из кнопок, вызывает функцию обработчика событий [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) загрузить соответствующие новую страницу.

Соответствующие части объявления класса (в CMyMultiPageDlg.h):

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

Соответствующие части реализации класса (в CMyMultipageDlg.cpp):

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog

Создает объект диалогового окна DHTML многостраничной (мастер в стиле).

```
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID = NULL,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog();
```

### <a name="parameters"></a>Параметры

*lpszTemplateName*<br/>
Завершающаяся нулем строка, представляющая имя ресурса шаблона диалогового окна.

*szHtmlResID*<br/>
Завершающаяся нулем строка, представляющая имя ресурса HTML.

*pParentWnd*<br/>
Указатель на объект окна родительский объект или владельца (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это значение NULL, родительское окно объекта диалогового окна будет присвоено главного окна приложения.

*nIDTemplate*<br/>
Содержит идентификатор ресурса шаблона диалогового окна.

*nHtmlResID*<br/>
Содержит идентификатор ресурса HTML.

##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog

Уничтожает объект многостраничной DHTML-диалоговое окно.

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>См. также

[Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
