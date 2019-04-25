---
title: Класс CWindowDC
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
ms.openlocfilehash: 55a9ccfc496c95c9e7410cbd5645135ee555ff26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323389"
---
# <a name="cwindowdc-class"></a>Класс CWindowDC

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
|[CWindowDC::m_hWnd](#m_hwnd)|HWND, к которому `CWindowDC` подключен.|

## <a name="remarks"></a>Примечания

Вызывает функцию Windows [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)во время создания и [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) во время уничтожения. Это означает, что `CWindowDC` объект производит доступ к целой области экрана [CWnd](../../mfc/reference/cwnd-class.md) (клиентские и неклиентские области).

Дополнительные сведения об использовании `CWindowDC`, см. в разделе [контексты устройств](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Требования

Header: afxwin.h

##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC

Создает `CWindowDC` объект, который обращается к целой области экрана (клиентские и неклиентские) `CWnd` объекта, на который указывает *pWnd*.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Окно которого клиентской области, будут получать доступ к объекту контекста устройства.

### <a name="remarks"></a>Примечания

Конструктор вызывает функцию Windows [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc).

Исключения (типа `CResourceException`) создается, если Windows `GetWindowDC` вызов завершается ошибкой. Контекст устройства не могут быть доступны в том случае, если Windows уже выделен все контексты его доступных устройств. Приложения конкурирует за пять общих отображения контексты, доступные в любой момент времени в группе Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd

HWND `CWnd` указатель используется для создания `CWindowDC` объекта.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

`m_hWnd` является защищенной переменной типа HWND.

### <a name="example"></a>Пример

  См. в примере [CWindowDC::CWindowDC](#cwindowdc).

## <a name="see-also"></a>См. также

[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
