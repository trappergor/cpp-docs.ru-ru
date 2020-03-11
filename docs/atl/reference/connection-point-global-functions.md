---
title: Глобальные функции точек подключения
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 0313e93ee82bb96f3bfe08e45f70ccfee30dbee6
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864408"
---
# <a name="connection-point-global-functions"></a>Глобальные функции точек подключения

Эти функции обеспечивают поддержку точек подключения и карт приемников.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|||
|-|-|
|[атладвисе](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|
|[атлунадвисе](#atlunadvise)|Завершает соединение, установленное с помощью `AtlAdvise`.|
|[атладвисесинкмап](#atladvisesinkmap)|Выдают или отменяют записи в карте приемника событий.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="atladvise"></a>атладвисе

Создает связь между точкой подключения объекта и приемником клиента.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Параметры

*пунккп*<br/>
окне Указатель на `IUnknown` объекта, с которым клиент хочет подключиться.

*pUnk*<br/>
окне Указатель на `IUnknown`клиента.

*IID*<br/>
окне Идентификатор GUID точки подключения. Как правило, это то же самое, что и исходящий интерфейс, управляемый точкой подключения.

*альтернатив*<br/>
заполняет Указатель на файл cookie, который однозначно определяет соединение.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Приемник реализует исходящий интерфейс, поддерживаемый точкой подключения. Клиент использует файл cookie *PDW* для удаления подключения, передав его в [атлунадвисе](#atlunadvise).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

##  <a name="atlunadvise"></a>атлунадвисе

Завершает соединение, установленное через [атладвисе](#atladvise).

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Параметры

*пунккп*<br/>
окне Указатель на `IUnknown` объекта, с которым соединен клиент.

*IID*<br/>
окне Идентификатор GUID точки подключения. Как правило, это то же самое, что и исходящий интерфейс, управляемый точкой подключения.

*dw*<br/>
окне Файл cookie, который однозначно определяет соединение.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

##  <a name="atladvisesinkmap"></a>атладвисесинкмап

Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Параметры

*Лутор*<br/>
окне Указатель на объект, содержащий карту приемника.

*бадвисе*<br/>
окне Значение TRUE, если все записи приемника должны быть рекомендованы. Значение FALSE, если все записи приемника должны быть нерекомендуемыми.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы для работы с точками подключения](../../atl/reference/connection-point-macros.md)
