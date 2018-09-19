---
title: с атрибутом naked (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89ab41c396f8602d16e2b2d88c3d83aeb7cdf21a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018386"
---
# <a name="naked-c"></a>naked (C++)

**Блок, относящийся только к системам Microsoft**

Для функций, объявленных с **с атрибутом naked** атрибут, компилятор создает код без кода пролога и эпилога. Эту возможность можно использовать, чтобы создавать свой собственный код на языке ассемблера и вставлять его в качестве пролога и эпилога. Функции с атрибутом naked особенно полезны для написания драйверов виртуальных устройств.  Обратите внимание, что **с атрибутом naked** атрибут допустим только для x86 и ARM и не доступен в x64.

## <a name="syntax"></a>Синтаксис

```
__declspec(naked) declarator
```

## <a name="remarks"></a>Примечания

Так как **с атрибутом naked** атрибут относится только к определению функции и не является модификатором типа, функции с атрибутом naked необходимо использовать расширенный синтаксис атрибутов и [__declspec](../cpp/declspec.md) ключевое слово.


Компилятор не может создать подставляемую функцию для функции, помеченной атрибутом naked, даже если функция помечена также [__forceinline](inline-functions-cpp.md) ключевое слово.

Компилятор выдает ошибку, если **с атрибутом naked** атрибут применяется только на определение метода, не являющихся членами.

## <a name="examples"></a>Примеры

Этот код определяет функцию с **с атрибутом naked** атрибут:

```
__declspec( naked ) int func( formal_parameters ) {}
```

Другой пример.

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

**С атрибутом naked** атрибут влияет только на создание кода компилятора для последовательностей пролога и эпилога функции. Код, который создается для вызова таких функций, не зависит от этого атрибута. Таким образом **с атрибутом naked** атрибут не является частью типа функции и указатели на функции не могут иметь **с атрибутом naked** атрибута. Кроме того **с атрибутом naked** атрибут не может использоваться для определения данных. Например, следующий код вызывает ошибку:

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

**С атрибутом naked** атрибут относится только к определению функции и не может указываться в прототипе функции. Например, следующее объявление создает ошибку компилятора:

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Вызовы функций с атрибутом naked](../cpp/naked-function-calls.md)