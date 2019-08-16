---
title: Класс Квиндовдк
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 0ef9b4917dc834eb8335690f9b0d171245f5c170
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502156"
---
# <a name="cwindowdc-class"></a>Класс Квиндовдк

Производное от `CDC`.

## <a name="syntax"></a>Синтаксис

```
class CWindowDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|Создает объект `CWindowDC`.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Квиндовдк:: m_hWnd](#m_hwnd)|HWND, к которому присоединен `CWindowDC` этот объект.|

## <a name="remarks"></a>Примечания

Вызывает функцию Windows [жетвиндовдк](/windows/win32/api/winuser/nf-winuser-getwindowdc)во время создания и [релеаседк](/windows/win32/api/winuser/nf-winuser-releasedc) в момент уничтожения. Это означает, что `CWindowDC` объект получает доступ ко всей области окна [CWnd](../../mfc/reference/cwnd-class.md) (как клиентские, так и неклиентские области).

Дополнительные сведения об использовании `CWindowDC`см. в разделе контексты [устройств](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Требования

Заголовок: AFXWIN. h

##  <a name="cwindowdc"></a>Квиндовдк:: Квиндовдк

Конструирует объект, обращающийся ко всей области экрана (как клиенту, так и к клиенту) `CWnd` объекта, на который указывает *приводится*. `CWindowDC`

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Окно, в клиентской области которого будет доступ объект контекста устройства.

### <a name="remarks"></a>Примечания

Конструктор вызывает функцию Windows [жетвиндовдк](/windows/win32/api/winuser/nf-winuser-getwindowdc).

Исключение (типа `CResourceException`) создается при сбое вызова Windows `GetWindowDC` . Контекст устройства может быть недоступен, если в Windows уже выделены все доступные контексты устройств. Приложение будет конкурировать за пять распространенных контекстов вывода, доступных в любой момент в Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>Квиндовдк:: m_hWnd

HWND `CWnd` указателя используется для `CWindowDC` создания объекта.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

`m_hWnd`— Это защищенная переменная типа HWND.

### <a name="example"></a>Пример

  См. пример для [квиндовдк:: квиндовдк](#cwindowdc).

## <a name="see-also"></a>См. также

[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
