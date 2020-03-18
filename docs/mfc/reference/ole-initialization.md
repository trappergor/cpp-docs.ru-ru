---
title: Инициализация OLE
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 6860697dd3adbe26197dd9075e84f402029e00a5
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426219"
---
# <a name="ole-initialization"></a>Инициализация OLE

Прежде чем приложение сможет использовать системные службы OLE, оно должно инициализировать системные библиотеки DLL OLE и убедиться, что библиотеки DLL имеют правильную версию. Функция `AfxOleInit` инициализирует системные DLL-библиотеки OLE.

### <a name="ole-initialization"></a>Инициализация OLE

|||
|-|-|
|[афксолеинит](#afxoleinit)|Инициализирует библиотеки OLE.|
|[афксенаблеконтролконтаинер](#afxenablecontrolcontainer)|Вызовите эту функцию в функции `InitInstance` объекта приложения, чтобы обеспечить поддержку включения элементов управления OLE.|

## <a name="afxenablecontrolcontainer"></a>афксенаблеконтролконтаинер

Вызовите эту функцию в функции `InitInstance` объекта приложения, чтобы обеспечить поддержку включения элементов управления OLE.

### <a name="syntax"></a>Синтаксис

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Remarks

Дополнительные сведения об элементах управления OLE (которые теперь называются элементами управления ActiveX) см. в [разделах элементы управления ActiveX](../mfc-activex-controls.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="afxoleinit"></a>афксолеинит

Инициализирует поддержку OLE для приложения.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; 0, если инициализация не удалась, возможно, установлены неверные версии системных библиотек OLE.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы инициализировать поддержку OLE для приложения MFC. При вызове этой функции выполняются следующие действия.

- Инициализирует библиотеку COM в текущем апартаменте вызывающего приложения. Дополнительные сведения см. в разделе [олеинитиализе](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- Создает объект фильтра сообщений, реализуя интерфейс [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) . Доступ к этому фильтру сообщений можно получить с помощью вызова [афксолежетмессажефилтер](application-control.md#afxolegetmessagefilter).

> [!NOTE]
>  Если **афксолеинит** вызывается из библиотеки DLL MFC, вызов завершится ошибкой. Сбой происходит из-за того, что функция предполагает, что, если она вызывается из библиотеки DLL, система OLE была ранее инициализирована вызывающим приложением.

> [!NOTE]
>  Приложения MFC должны быть инициализированы как однопотоковое подразделение (STA). При вызове [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в переопределении `InitInstance` укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
