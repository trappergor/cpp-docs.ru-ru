---
title: Класс vector&lt;bool&gt;::reference | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- vector/vector<bool>::reference
dev_langs:
- C++
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05486e4b75e631dcdc77855e850fe48c08d77326
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203855"
---
# <a name="vectorltboolgtreference-class"></a>Класс vector&lt;bool&gt;::reference

Класс `vector<bool>::reference` — это прокси-класс, предоставленный классом [vector\<bool> ](../standard-library/vector-bool-class.md) для моделирования `bool&`.

## <a name="remarks"></a>Примечания

Необходима смоделированная ссылка, поскольку C++ изначально не допускает прямых ссылок на биты. `vector<bool>` использует только один бит на элемент, ссылку на который можно создать с помощью данного класса прокси. Однако моделирование ссылки является незавершенным, поскольку определенные назначения не являются допустимыми. Например, следующий пример использования объекта [vector\<bool>::operator[]](https://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd) является неправильным, так как невозможно получить адрес объекта `vector<bool>::reference`.

```cpp
vector<bool> vb;
// ...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
|-|-|
|[flip](../standard-library/vector-bool-reference-flip.md)|Инвертирует логическое значение элемента вектора.|
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|Предоставляет неявное преобразование из `vector<bool>::reference` для **bool**.|
|[оператор=](../standard-library/vector-bool-reference-operator-assign.md)|Присваивает биту логическое значение или значение, которое содержит элемент со ссылкой.|

## <a name="requirements"></a>Требования

**Заголовок:** \<vector>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<vector>](../standard-library/vector.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
