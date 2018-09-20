---
title: Типы данных OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b41eaf7012c1d119071281f98177e4a4d841890b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410077"
---
# <a name="openmp-data-types"></a>Типы данных OpenMP

Содержит ссылки на типы данных, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие типы данных.

|Тип данных|Описание|
|---------------|-----------------|
|[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)|Тип, содержащий состояние блокировки, доступен ли блокировка, или если поток владеет блокировкой.|
|[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)|Тип, содержащий один из следующих элементов информации о блокировке: ли доступна блокировка, и идентификатор потока, которому принадлежит блокировка и вложенности счетчик.|

## <a name="see-also"></a>См. также

[Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)