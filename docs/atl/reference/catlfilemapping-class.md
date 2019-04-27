---
title: Класс CAtlFileMapping
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: d0a47a6cf0cc86409ceb9ef40d6fc6d738c86aa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247177"
---
# <a name="catlfilemapping-class"></a>Класс CAtlFileMapping

Этот класс представляет размещенного в памяти файла, добавление оператора приведения к методам [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, используемых для оператора приведения.

## <a name="members"></a>Участники

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CAtlFileMapping::operator T *](#operator_t_star)|Позволяет выполнять неявное преобразование из `CAtlFileMapping` объектов `T*`.|

## <a name="remarks"></a>Примечания

Этот класс добавляет оператор единый приведения, чтобы разрешить неявное преобразование `CAtlFileMapping` объектов `T*`. Другие члены передаются в базовом классе [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *

Позволяет выполнять неявное преобразование из `CAtlFileMapping` объектов `T*`.

```
operator T*() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `T*` указатель на начало файла размещенный в памяти.

### <a name="remarks"></a>Примечания

Вызовы [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) и повторно интерпретирует возвращенный указатель как `T*` где *T* является типом, используемым как параметр шаблона этого класса.

## <a name="see-also"></a>См. также

[Класс CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
