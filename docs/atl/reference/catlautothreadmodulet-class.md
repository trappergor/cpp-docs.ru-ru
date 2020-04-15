---
title: Класс CAtlAutoThreadModulet
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: e7b7a327d7c47c4472b43ed58fbe9ad0556a7620
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321543"
---
# <a name="catlautothreadmodulet-class"></a>Класс CAtlAutoThreadModulet

Этот класс предоставляет методы для реализации сервера COM, объединенного потоками, с моделью апартаментов.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, который будет реализовывать сервер COM.

*ThreadAllocator*<br/>
Класс, управляющий выбором потоков. Значение по умолчанию [— CComSimpleThreadAllocator.](../../atl/reference/ccomsimplethreadallocator-class.md)

*dwWait*<br/>
Определяет интервал тайм-аута в миллисекундах. По умолчанию по умолчанию, что означает, что интервал тайм-аута метода никогда не проходит.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля EXE, в зависимости от количества процессоров.|

## <a name="remarks"></a>Remarks

Класс [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) происходит `CAtlAutoThreadModuleT` от для реализации поток-объединенный, квартира-модель COM сервера. Он заменяет устаревший класс [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

> [!NOTE]
> Этот класс не должен использоваться в DLL, так как значение *dwWait* по умолчанию INFINITE приведет к тупику при выгрузке DLL.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads

Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля EXE, в зависимости от количества процессоров.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Возвращаемое значение

Количество потоков, которые будут созданы в модуле EXE.

### <a name="remarks"></a>Remarks

Переопределить этот метод, если вы хотите использовать другой метод для расчета количества потоков. По умолчанию количество потоков зависит от количества процессоров.

## <a name="see-also"></a>См. также раздел

[IAtlAutoThreadModule Класс](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule Класс](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
