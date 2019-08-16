---
title: Класс Кклиентдк
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: 46428740d052c70218d4443395777428cdf3c3b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507341"
---
# <a name="cclientdc-class"></a>Класс Кклиентдк

Позаботится о вызове функций Windows, [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) во время создания и [релеаседк](/windows/win32/api/winuser/nf-winuser-releasedc) в момент уничтожения.

## <a name="syntax"></a>Синтаксис

```
class CClientDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|Конструирует объект, `CWnd`подключенныйк. `CClientDC`|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Кклиентдк:: m_hWnd](#m_hwnd)|HWND окна, для которого это `CClientDC` допустимо.|

## <a name="remarks"></a>Примечания

Это означает, что контекст устройства, связанный с `CClientDC` объектом, является клиентской областью окна.

Дополнительные сведения о см `CClientDC`. в разделе [контексты устройств](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cclientdc"></a>Кклиентдк:: Кклиентдк

Конструирует объект, обращающийся к клиентской области [CWnd](../../mfc/reference/cwnd-class.md) , на которую указывает приводится. `CClientDC`

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Окно, в клиентской области которого будет доступ объект контекста устройства.

### <a name="remarks"></a>Примечания

Конструктор вызывает функцию Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc).

Исключение (типа `CResourceException`) создается при сбое вызова Windows `GetDC` . Контекст устройства может быть недоступен, если в Windows уже выделены все доступные контексты устройств. Приложение будет конкурировать за пять распространенных контекстов вывода, доступных в любой момент в Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>Кклиентдк:: m_hWnd

`HWND` Объект`CWnd` указателя,используемый`CClientDC` для создания объекта.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

*m_hWnd* — это защищенная переменная.

### <a name="example"></a>Пример

  См. пример для [кклиентдк:: кклиентдк](#cclientdc).

## <a name="see-also"></a>См. также

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
