---
title: '&lt;InstancePersistenceCommand&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: f37458fdc0b58968e095a7c59de797eac295bde7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835940"
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

|Имя|Описание|
|-|-|
|[Структура is_execution_policy](is-execution-policy-struct.md)|Обнаруживает политики выполнения в целях исключения сигнатур функций из неоднозначного участия в разрешении перегрузки.|
|[Класс parallel_policy](parallel-policy-class.md)|Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и указывает, что выполнение параллельного алгоритма может быть параллельным.|
|[Класс parallel_unsequenced_policy](parallel-unsequenced-policy-class.md)|Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и указывает, что выполнение параллельного алгоритма может быть параллельным и векторным.|
|[Класс sequenced_policy](sequenced-policy-class.md)|Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и требует, чтобы выполнение параллельного алгоритма не было параллельным.|

## <a name="requirements"></a>Требования

**Заголовок:**\<execution>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](cpp-standard-library-reference.md)
