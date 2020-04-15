---
title: Маршалинг Глобальные функции
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: b839e93b6251a09ce79df60a49b4054d1af76cc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326263"
---
# <a name="marshaling-global-functions"></a>Маршалинг Глобальные функции

Эти функции обеспечивают поддержку для маршалинга и преобразования маршалингинг данных в указатели интерфейса.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Выпускает данные маршала и указатель. `IStream`|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Создает новый объект потока и маршалов указанный указатель интерфейса.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|Преобразует данные потока в указатель интерфейса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a>AtlFreeMarshalStream

Освобождает данные маршалинга в потоке, затем освобождает указатель потока.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
(в) Указатель на `IStream` интерфейс в потоке, используемом для маршалинга.

### <a name="example"></a>Пример

Смотрите пример [для AtlMarshalPtrInProc](#atlmarshalptrinproc).

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a>"Атлетико"

Создает новый объект потока, записывает в поток CLSID прокси-сервера и маршалирует заданный указатель интерфейса, записывая в поток данные, необходимые для инициализации прокси-сервера.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на интерфейс, который должен быть маршализирован.

*Iid*<br/>
(в) GUID интерфейса, который подвергается маршалу.

*ppStream*<br/>
(ваут) Указатель на `IStream` интерфейс нового объекта потока, используемого для маршалинга.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Флаг MSHLFLAGS_TABLESTRONG установлен таким образом, чтобы указатель мог быть приспущен на несколько потоков. Указатель также может быть неmarshaled несколько раз.

При сбой в маршалах высвобождается указатель потока.

`AtlMarshalPtrInProc`может быть использован только на указателе на объект в процессе.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a>АтлетикоПмаршалТр

Преобразует данные маршалинга потока в указатель интерфейса, который может использоваться клиентом.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
(в) Указатель на поток неmarshaled.

*Iid*<br/>
(в) GUID интерфейса быть неmarshaled.

*ppUnk*<br/>
(ваут) Указатель на немаршалированный интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

Смотрите пример [для AtlMarshalPtrInProc](#atlmarshalptrinproc).

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
