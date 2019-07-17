---
title: '&lt;Выполнение&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3bce34019f9ed4880d72a9d16c3c8b78dde0e0e3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268426"
---
# <a name="ltexecutiongt"></a>&lt;Выполнение&gt;

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
|[is_execution_policy структуры](is-execution-policy-struct.md)|Определяет политики выполнения для целей за исключением сигнатур функций из участия в противном случае неоднозначная перегрузка разрешения.|
|[Класс parallel_policy](parallel-policy-class.md)|Используется как уникальный тип для устранения неоднозначности перегрузки параллельный алгоритм и указать, что выполнение параллельного алгоритма может выполняться параллельно.|
|[Класс parallel_unsequenced_policy](parallel-unsequenced-policy-class.md)|Используется как уникальный тип для устранения неоднозначности перегрузки параллельный алгоритм и указать, что параллельный алгоритм выполнения может быть параллелизован и преобразованы в векторный формат.|
|[Класс sequenced_policy](sequenced-policy-class.md)|Используется как уникальный тип для устранения неоднозначности перегрузки параллельного алгоритма и требуют, что выполнение параллельного алгоритма не может выполняться параллельно.|

## <a name="requirements"></a>Требования

**Заголовок:** \<выполнения >

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](cpp-standard-library-reference.md)
