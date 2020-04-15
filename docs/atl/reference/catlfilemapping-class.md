---
title: Класс CAtlFileMapping
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: ca46ccdacf5ea24f1de26cdc75bf808c4ecfaa40
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318960"
---
# <a name="catlfilemapping-class"></a>Класс CAtlFileMapping

Этот класс представляет собой файл с картографом памяти, добавляя литого оператора к методам [CAtlFileMappingBase.](../../atl/reference/catlfilemappingbase-class.md)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, используемых для литой оператора.

## <a name="members"></a>Участники

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlFileMapping::оператор ТЗ](#operator_t_star)|Позволяет неявное преобразование объектов `CAtlFileMapping` в `T*`.|

## <a name="remarks"></a>Remarks

Этот класс добавляет одного оператора литых, чтобы позволить неявное преобразование объектов `CAtlFileMapping` в `T*`. Другие участники поставляются базовым классом, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFileMapping::оператор ТЗ

Позволяет неявное преобразование объектов `CAtlFileMapping` в `T*`.

```
operator T*() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

`T*` Возвращает указатель на начало файла с картой памяти.

### <a name="remarks"></a>Remarks

Вызывает [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) и переосмысливает возвращенный `T*` указатель как тип *T,* используемый в качестве параметра шаблона этого класса.

## <a name="see-also"></a>См. также раздел

[Класс CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
