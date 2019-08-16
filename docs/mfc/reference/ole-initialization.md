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
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502028"
---
# <a name="ole-initialization"></a>Инициализация OLE

Прежде чем приложение сможет использовать системные службы OLE, оно должно инициализировать системные библиотеки DLL OLE и убедиться, что библиотеки DLL имеют правильную версию. `AfxOleInit` Функция инициализирует системные DLL-библиотеки OLE.

### <a name="ole-initialization"></a>Инициализация OLE

|||
|-|-|
|[афксолеинит](#afxoleinit)|Инициализирует библиотеки OLE.|
|[афксенаблеконтролконтаинер](#afxenablecontrolcontainer)|Вызовите эту функцию в `InitInstance` функции объекта приложения, чтобы обеспечить поддержку включения элементов управления OLE.|

## <a name="afxenablecontrolcontainer"></a>афксенаблеконтролконтаинер

Вызовите эту функцию в `InitInstance` функции объекта приложения, чтобы обеспечить поддержку включения элементов управления OLE.

### <a name="syntax"></a>Синтаксис

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Примечания

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

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы инициализировать поддержку OLE для приложения MFC. При вызове этой функции выполняются следующие действия.

- Инициализирует библиотеку COM в текущем апартаменте вызывающего приложения. Дополнительные сведения см. в разделе [олеинитиализе](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- Создает объект фильтра сообщений, реализуя интерфейс [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) . Доступ к этому фильтру сообщений можно получить с помощью вызова [афксолежетмессажефилтер](application-control.md#afxolegetmessagefilter).

> [!NOTE]
>  Если **афксолеинит** вызывается из библиотеки DLL MFC, вызов завершится ошибкой. Сбой происходит из-за того, что функция предполагает, что, если она вызывается из библиотеки DLL, система OLE была ранее инициализирована вызывающим приложением.

> [!NOTE]
>  Приложения MFC должны быть инициализированы как однопотоковое подразделение (STA). При вызове [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в `InitInstance` переопределении укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
