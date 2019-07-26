---
title: '&lt;InstancePersistenceCommand&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3b0ccd540c56500c2f265aa6192a12fc2d5078b0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457968"
---
# <a name="ltexecutiongt"></a>&lt;InstancePersistenceCommand&gt;

Описывает политики выполнения для параллельных алгоритмов.

## <a name="syntax"></a>Синтаксис

```
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```
### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|[Структура is_execution_policy](is-execution-policy-struct.md)|Обнаруживает политики выполнения в целях исключения сигнатур функций из неоднозначного участия в разрешении перегрузки.|
|[Класс parallel_policy](parallel-policy-class.md)|Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и указывает, что выполнение параллельного алгоритма может быть параллельным.|
|[Класс parallel_unsequenced_policy](parallel-unsequenced-policy-class.md)|Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и указывает, что выполнение параллельного алгоритма может быть параллельным и векторным.|
|[Класс sequenced_policy](sequenced-policy-class.md)|Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и требует, чтобы выполнение параллельного алгоритма не было параллельным.|

## <a name="requirements"></a>Требования

**Заголовок:** \<> выполнения

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](cpp-standard-library-reference.md)
