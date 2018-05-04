---
title: Передача аргументов CString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 642ff20028a0929bb7bc11815e66b9f845ef9bd7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cstring-argument-passing"></a>Передача аргументов CString
В этой статье объясняется, как передать [CString](../atl-mfc-shared/reference/cstringt-class.md) объектов функций и как вернуть `CString` объекты из функции.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> Соглашения о передаче аргументов CString  
 При определении интерфейса класса, необходимо определить соглашение о передаче аргументов для функций-членов. Существуют некоторые стандартные правила, передачу и возврат `CString` объектов. Если следовать правилам, описанным в [строки в качестве входных данных функции](#_core_strings_as_function_inputs) и [строки как выходные данные функции](#_core_strings_as_function_outputs), будет иметь эффективный и правильный код.  
  
##  <a name="_core_strings_as_function_inputs"></a> Строки в качестве входных данных функции  
 Наиболее эффективный и безопасный способ использования `CString` объект в вызываемой функции заключается в передаче `CString` объекта функции. Несмотря на название `CString` объекта не строка внутренних целей Сохранить как строка C-стиле, которая имеет значение NULL. Вместо этого `CString` объекта будет тщательно отслеживать количество символов, он имеет. Наличие `CString` предоставляют `LPCTSTR` небольшой объем работы, которая может стать существенным, если код содержит постоянно сделать это является указателем на строку, завершающуюся значением null. Результат является временным, так как после любого изменения `CString` содержимое делает недействительными старые копии `LPCTSTR` указателя.  
  
 Оно имеет смысла в некоторых случаях для предоставления строки в стиле C. Например может быть ситуация, где вызываемая функция написана на языке C, а не поддерживает объекты. В этом случае приведение `CString` параметр `LPCTSTR`, и функция получает строку, завершающуюся символом null C-стиле. Кроме того, можно перейти в обратном направлении и создавать `CString` объектов с помощью `CString` конструктор, принимающий строковый параметр C-стиле.  
  
 Если содержимое строки будут изменены функцией, объявите параметр как неконстантной `CString` ссылки (**CString &**).  
  
##  <a name="_core_strings_as_function_outputs"></a> Строки как выходные данные функции  
 Обычно можно вернуть `CString` объектов из функции, так как `CString` объекты следуют семантика значения как простые типы. Для возврата строки, только для чтения, используйте константу `CString` ссылки (**const CString &**). Следующий пример иллюстрирует использование `CString` параметры и возвращаемые типы:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)

