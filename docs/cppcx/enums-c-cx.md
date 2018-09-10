---
title: Перечисления (C + +/ CX) | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fff0ffb62182e078149d1403c495c69ae918c36
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105728"
---
# <a name="enums-ccx"></a>Перечисления (C++/CX)

C + +/ CX поддерживает `public enum class` ключевое слово, которое является аналогом standard C++ `scoped  enum`. При использовании перечислителя, объявленного с помощью ключевого слова `public enum class` , необходимо использовать идентификатор перечисления, чтобы определить область каждого значения перечислителя.

### <a name="remarks"></a>Примечания

Объявление `public enum class` , не содержащее спецификатор доступа, например `public`, обрабатывается как стандартное [перечисление С++ с областью видимости](../cpp/enumerations-cpp.md).

Объект `public enum class` или `public enum struct` объявление может иметь базовый тип любого целочисленного типа, несмотря на то, что в самой среде выполнения Windows требует тип int32 или uint32 для перечислений флагов. Следующий синтаксис описывает части объявления `public enum class` или `public enum struct`.

В этом примере показано, как определить открытый класс перечисления:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

В следующем примере показано, как использовать его:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Примеры

В следующих примерах показано, как объявить перечисление.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

В следующем примере показано, как выполнять приведение к числовым эквивалентами и выполнять сравнения. Обратите внимание, что область использования перечислителя `One` определяется идентификатором перечисления `Enum1` , а область использования перечислителя `First` — идентификатором `Enum2`.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>См. также

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)