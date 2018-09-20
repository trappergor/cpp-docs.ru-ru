---
title: firstprivate | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d070b8de3cf0382447c3b8e756140892dcd85edc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387124"
---
# <a name="firstprivate"></a>firstprivate

Указывает, что каждый поток должен иметь свой собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, так как она существует до параллельной конструкции.

## <a name="syntax"></a>Синтаксис

```
firstprivate(var)
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`var`|Переменная экземпляров в каждом потоке, которые будет инициализирован со значением переменной, так как она существует до параллельной конструкции. Если указано более одной переменной, разделите имена переменных запятыми.|

## <a name="remarks"></a>Примечания

## <a name="remarks"></a>Примечания

`firstprivate` область применения следующих директив:

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [Разделы](../../../parallel/openmp/reference/sections-openmp.md)

- [single](../../../parallel/openmp/reference/single.md)

Дополнительные сведения см. в разделе [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).

## <a name="example"></a>Пример

Например, с помощью `firstprivate`, см. пример в [частного](../../../parallel/openmp/reference/private-openmp.md).

## <a name="see-also"></a>См. также

[Предложения](../../../parallel/openmp/reference/openmp-clauses.md)