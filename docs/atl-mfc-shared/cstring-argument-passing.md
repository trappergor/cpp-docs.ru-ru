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
ms.openlocfilehash: bf18265e19e4b1c1db010a4d7638fa959c357bca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562400"
---
# <a name="cstring-argument-passing"></a>Передача аргументов CString

В этой статье объясняется, как передать [CString](../atl-mfc-shared/reference/cstringt-class.md) объектов для функций и как вернуть `CString` объектов из функции.

##  <a name="_core_cstring_argument.2d.passing_conventions"></a> Соглашения о передаче аргументов CString

При определении интерфейса класса, необходимо определить соглашение о передаче аргументов для функций-членов. Существуют некоторые стандартные правила для передачи и возврата `CString` объектов. При выполнении правила, описанные в [строки в качестве входных данных функции](#_core_strings_as_function_inputs) и [строки как выходные данные функции](#_core_strings_as_function_outputs), вы получите эффективный и правильный код.

##  <a name="_core_strings_as_function_inputs"></a> Строки в качестве входных данных функции

Наиболее эффективный и безопасный способ использования `CString` является передача объекта в вызываемые функции `CString` объекта функции. Несмотря на название `CString` объекта не хранит строка внутренне как строка C-стиля, которая имеет завершающий нуль-символ. Вместо этого `CString` хранит количество символов, он имеет подробная запись. Наличие `CString` предусмотрен небольшой объем работы, которая может стать значительной в том случае, если код содержит сделать его постоянно LPCTSTR указатель на строку, завершающуюся символом null. Результат является временным, так как после любого изменения `CString` содержимое делает недействительным старые копии LPCTSTR указателя.

Он имеет смысл в некоторых случаях для предоставления строки C-стиля. Например может быть ситуация, где создается на языке C вызываемой функции и не поддерживает объекты. В этом случае приведение `CString` параметр LPCTSTR, а функция получит заканчивающуюся нулем строку C-стиля. Можно также перейти в обратном направлении и создать `CString` объекта с помощью `CString` конструктор, принимающий строковый параметр C-стиля.

Если содержимое строки будут изменены функцией, объявите параметр как неконстантной `CString` ссылки (`CString&`).

##  <a name="_core_strings_as_function_outputs"></a> Строки, как выходные данные функции

Обычно можно вернуться `CString` объектов из функций, так как `CString` объекты следуют семантике значение как простые типы. Чтобы вернуть строку только для чтения, используйте константу `CString` ссылки (`const CString&`). Следующий пример иллюстрирует использование `CString` параметрам и возвращаемым типам:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

