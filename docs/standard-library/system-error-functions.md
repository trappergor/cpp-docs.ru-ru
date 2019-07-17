---
title: Функции &lt;system_error&gt;
ms.date: 03/15/2019
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: ab4d0d1ee810df8f719bba762262eb03bf899408
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245107"
---
# <a name="ltsystemerrorgt-functions"></a>Функции &lt;system_error&gt;

## <a name="generic_category"></a> generic_category

Представляет категорию общих ошибок.

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>Примечания

`generic_category` Объект представляет собой реализацию [error_category](../standard-library/error-category-class.md).

## <a name="is_error_code_enum_v"></a> is_error_code_enum_v

```cpp
template <class T> 
    inline constexpr bool is_error_code_enum_v = is_error_code_enum<T>::value;
```

## <a name="is_error_condition_enum_v"></a> is_error_condition_enum_v

```cpp
template <class T> 
    inline constexpr bool is_error_condition_enum_v = is_error_condition_enum<T>::value;
```

## <a name="make_error_code"></a> make_error_code

Создает объект кода ошибки.

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>Параметры

*Ошибка*\
`std::errc` Значение перечисления для хранения в объекте кода ошибки.

### <a name="return-value"></a>Возвращаемое значение

Объект кода ошибки.

### <a name="remarks"></a>Примечания

## <a name="make_error_condition"></a> make_error_condition

Создает объект условия ошибки.

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>Параметры

*Ошибка*\
`std::errc` Значение перечисления для хранения в объекте кода ошибки.

### <a name="return-value"></a>Возвращаемое значение

Объект условия ошибки.

### <a name="remarks"></a>Примечания

## <a name="system_category"></a> system_category

Представляет категорию ошибок, вызванных переполнением системы низкого уровня.

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>Примечания

`system_category` Объект представляет собой реализацию [error_category](../standard-library/error-category-class.md).
