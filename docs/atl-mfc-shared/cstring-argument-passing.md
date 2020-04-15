---
title: Передача аргументов CString
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: 53977eb47520a20571a2d5ba8aa105c567ff40d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317935"
---
# <a name="cstring-argument-passing"></a>Передача аргументов CString

В этой статье объясняется, как передавать объекты [CString](../atl-mfc-shared/reference/cstringt-class.md) функциям и как возвращать `CString` объекты из функций.

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a>CString Аргумент-проходя конвенций

При определении интерфейса класса необходимо определить конвенцию, передаваемую аргументами, для ваших функций члена. Существуют некоторые стандартные правила `CString` для передачи и возвращения объектов. Если вы будете следовать правилам, описанным в [строках как функциональные входы](#_core_strings_as_function_inputs) и [строки как выходы функций,](#_core_strings_as_function_outputs)у вас будет эффективный, правильный код.

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a>Строки как входные данные функций

Наиболее эффективным и безопасным `CString` способом использования объекта `CString` в вызванных функциях является передача объекта функции. Несмотря на `CString` название, объект не хранит строку внутри как строку C-стиля, которая имеет нулевой терминатор. Вместо этого `CString` объект внимательно отслеживает количество символов, которые у него есть. Предоставление `CString` указателя LPCTSTR на нулевую строку представляет собой небольшой объем работы, который может стать значительным, если ваш код должен делать это постоянно. Результат носит временный характер, `CString` поскольку любое изменение содержимого аннулирует старые копии указателя LPCTSTR.

В некоторых случаях имеет смысл предоставить строку в стиле C. Например, может возникнуть ситуация, когда вызванная функция написана на C и не поддерживает объекты. В этом случае принудить `CString` параметр к LPCTSTR, и функция получит строку с нулом. Вы также можете пойти в `CString` другом направлении и создать объект с помощью `CString` конструктора, который принимает параметр строки C-стиля.

Если содержимое строки должно быть изменено функцией, `CString` объявите`CString&`параметр непостоянной ссылкой ().

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a>Строки как выходы функций

Обычно можно `CString` вернуть объекты `CString` из функций, поскольку объекты следуют семантике значений, как примитивные типы. Чтобы вернуть строку только для `CString` чтения,`const CString&`используйте постоянную ссылку (). Следующий пример иллюстрирует использование `CString` параметров и типов возврата:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Струны (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
