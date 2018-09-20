---
title: lastprivate | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7124e51b604a55d049be13d3bbcccc4e5810ca67
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412838"
---
# <a name="lastprivate"></a>lastprivate

Указывает, что версия переменной в охватывающем контексте приравнивается к закрытой версии потока, который выполняет последней итерации (конструкция цикл "for") или последний раздел (#pragma разделов).

## <a name="syntax"></a>Синтаксис

```
lastprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Переменная, которая задана равной закрытой версии потока, который выполняет последней итерации (конструкция цикл "for") или последний раздел (#pragma разделов).

## <a name="remarks"></a>Примечания

`lastprivate` область применения следующих директив:

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Разделы](../../../parallel/openmp/reference/sections-openmp.md)

Дополнительные сведения см. в разделе [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).

## <a name="example"></a>Пример

См. в разделе [расписание](../../../parallel/openmp/reference/schedule.md) пример использования `lastprivate` предложение.

## <a name="see-also"></a>См. также

[Предложения](../../../parallel/openmp/reference/openmp-clauses.md)