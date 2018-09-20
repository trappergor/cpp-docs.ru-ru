---
title: по умолчанию (OpenMP) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ea32f473d96c8f48c6628d8f71212269bd6d345
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392620"
---
# <a name="default-openmp"></a>default (OpenMP)

Задает поведение неограниченного переменных в параллельной области.

## <a name="syntax"></a>Синтаксис

```
default(shared | none)
```

## <a name="remarks"></a>Примечания

`shared`, который является по сути Если `default` предложение не указано, означает, что любой переменной в параллельной области должен рассматриваться, как если бы он был указан с [общего](../../../parallel/openmp/reference/shared-openmp.md) предложение. `none` означает, что все переменные, используемые в параллельной области, не ограничены областью с [частного](../../../parallel/openmp/reference/private-openmp.md), [общего](../../../parallel/openmp/reference/shared-openmp.md), [сокращения](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), или [lastprivate](../../../parallel/openmp/reference/lastprivate.md) предложение приведет к ошибке компилятора.

`default` область применения следующих директив:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Разделы](../../../parallel/openmp/reference/sections-openmp.md)

Дополнительные сведения см. в разделе [2.7.2.5 по умолчанию](../../../parallel/openmp/2-7-2-5-default.md).

## <a name="example"></a>Пример

См. в разделе [частного](../../../parallel/openmp/reference/private-openmp.md) пример использования `default`.

## <a name="see-also"></a>См. также

[Предложения](../../../parallel/openmp/reference/openmp-clauses.md)