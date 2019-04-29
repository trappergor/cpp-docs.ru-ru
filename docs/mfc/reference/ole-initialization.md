---
title: Инициализация OLE
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 3d49b37ffc2561fa9a51463a893ec2ba4f4fb725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310282"
---
# <a name="ole-initialization"></a>Инициализация OLE

Прежде чем приложение может использовать OLE системные службы, его необходимо инициализировать OLE системные библиотеки DLL и убедитесь, что библиотеки DLL нужной версии. `AfxOleInit` Функция инициализирует OLE системные библиотеки DLL.

### <a name="ole-initialization"></a>Инициализация OLE

|||
|-|-|
|[AfxOleInit](#afxoleinit)|Инициализирует библиотек OLE.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Вызовите эту функцию в объект приложения `InitInstance` функции, чтобы включить поддержку для включения элементов управления OLE.|

## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer

Вызовите эту функцию в объект приложения `InitInstance` функции, чтобы включить поддержку для включения элементов управления OLE.

### <a name="syntax"></a>Синтаксис

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Примечания

Дополнительные сведения об элементах управления OLE (теперь называется элементы управления ActiveX), см. в разделе [разделов элемента управления ActiveX](../mfc-activex-controls.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="afxoleinit"></a>  AfxOleInit

Инициализирует OLE поддержку для приложения.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; 0, если инициализация не будет выполнена, возможно потому, что установлены неправильные версии системных библиотек OLE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для инициализации поддержки OLE для приложения MFC. При вызове этой функцией, выполняются следующие действия:

- Инициализирует библиотеку COM в текущем подразделении вызывающего приложения. Дополнительные сведения см. в разделе [OleInitialize](/windows/desktop/api/ole2/nf-ole2-oleinitialize).

- Создает объект фильтра сообщения реализация [IMessageFilter](/windows/desktop/api/objidl/nn-objidl-imessagefilter) интерфейс. Этот фильтр сообщений может осуществляться с помощью вызова [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

> [!NOTE]
>  Если **AfxOleInit** вызывается из библиотеки DLL MFC, вызов завершится ошибкой. Сбой происходит, так как функция предполагает, что, если он вызывается из библиотеки DLL, система OLE ранее был инициализирован в вызывающем приложении.

> [!NOTE]
>  MFC-приложения должны инициализироваться как однопотоковое подразделение (STA). При вызове метода [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) в вашей `InitInstance` переопределения, укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
