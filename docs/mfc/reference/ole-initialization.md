---
title: Инициализация OLE
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 39a6f28bfe38f254f15f441ed6305daa2cb5793e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373032"
---
# <a name="ole-initialization"></a>Инициализация OLE

Прежде чем приложение сможет использовать системные службы OLE, оно должно инициализировать DLL системы OLE и убедиться, что DLL являются правильной версией. Функция `AfxOleInit` инициализирует DLL системы OLE.

### <a name="ole-initialization"></a>Инициализация OLE

|||
|-|-|
|[AfxOleInit](#afxoleinit)|Инициализирует библиотеки OLE.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Вызовите эту функцию `InitInstance` в функции объекта приложения, чтобы обеспечить поддержку сдерживания элементов управления OLE.|

## <a name="afxenablecontrolcontainer"></a><a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer

Вызовите эту функцию `InitInstance` в функции объекта приложения, чтобы обеспечить поддержку сдерживания элементов управления OLE.

### <a name="syntax"></a>Синтаксис

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о элементах управления OLE (теперь называется ActiveX управления), см [ActiveX Управления Темы](../mfc-activex-controls.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="afxoleinit"></a><a name="afxoleinit"></a>AfxOleInit

Инициализирует поддержку ПРИЛОЖЕНИЯ OLE.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; 0, если инициализация не удается, возможно, потому, что неправильные версии системы OLE DLLs установлены.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы инициализировать поддержку OLE для приложения MFC. Когда эта функция вызывается, возникают следующие действия:

- Инициализирует библиотеку COM на текущей квартире вызывающей заявки. Для получения дополнительной информации, см [Ole Initialize](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- Создает объект фильтра сообщений, реализуя интерфейс [IMessageFilter.](/windows/win32/api/objidl/nn-objidl-imessagefilter) Этот фильтр сообщений можно получить с помощью вызова [на AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

> [!NOTE]
> Если **AfxOleInit** вызывается из MFC DLL, вызов не удастся. Сбой происходит потому, что функция предполагает, что, если она называется из DLL, система OLE была ранее инициализирована вызывающей приложением.

> [!NOTE]
> Приложения МФЦ должны быть инициализированы как одноразовая квартира (STA). Если вы звоните [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в переопределении, `InitInstance` укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
