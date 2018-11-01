---
title: Программирование с использованием CComBSTR (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 44689b45d567c524d6db1446cd65201c21499c91
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633120"
---
# <a name="programming-with-ccombstr-atl"></a>Программирование с использованием CComBSTR (ATL)

Класс ATL [CComBSTR](../atl/reference/ccombstr-class.md) обеспечивает создание оболочки данные типа BSTR. Хотя `CComBSTR` — это полезное средство, существует несколько ситуаций, требующих осторожность.

- [Проблемы преобразования](#programmingwithccombstr_conversionissues)

- [Область проблемы](#programmingwithccombstr_scopeissues)

- [Явное освобождение объекта CComBSTR](#programmingwithccombstr_explicitlyfreeing)

- [Использование CComBSTR объектов в циклах](#programmingwithccombstr_usingloops)

- [Проблемы утечки памяти](#programmingwithccombstr_memoryleaks)

##  <a name="programmingwithccombstr_conversionissues"></a> Проблемы преобразования

Несмотря на то что несколько `CComBSTR` методы автоматически преобразует передан аргумент строки ANSI в Юникод, методы всегда возвращают строки формата Юникод. Чтобы преобразовать выходной строки ANSI, используйте класс ATL преобразования. Дополнительные сведения о преобразовании классы ATL, см. в разделе [ATL и макросов преобразования MFC из строки](reference/string-conversion-macros.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

При использовании строкового литерала для изменения `CComBSTR` , используйте строки расширенных символов. Это позволит снизить ненужных преобразований.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

##  <a name="programmingwithccombstr_scopeissues"></a> Область проблемы

Как и в случае с любой обретают класс `CComBSTR` будет освобождения ее ресурсов, если он выходит за пределы области. Если функция возвращает указатель на `CComBSTR` строки, это может вызвать проблемы, поскольку указатель будет ссылаться памяти, который уже был освобожден. В таких случаях используйте `Copy` метод, как показано ниже.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

##  <a name="programmingwithccombstr_explicitlyfreeing"></a> Явное освобождение объекта CComBSTR

Можно явно освободить строку, содержащуюся в `CComBSTR` прежде, чем объект выходит из области. Если строка освобождается, `CComBSTR` недопустимый объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

##  <a name="programmingwithccombstr_usingloops"></a> Использование CComBSTR объектов в циклах

Как `CComBSTR` класс выделяет буфер для выполнения определенных операций, таких как `+=` оператор или `Append` метод, не рекомендуется выполнять строками в непрерывном цикле. В таких ситуациях `CStringT` обеспечивает более высокую производительность.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

##  <a name="programmingwithccombstr_memoryleaks"></a> Проблемы утечки памяти

Передав адрес инициализированный `CComBSTR` выступать в качестве **[out]** параметра приводит к утечке памяти.

В следующем примере строки, выделенные для хранения строки `"Initialized"` происходит утечка когда функция `MyGoodFunction` заменяет строку.

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

Чтобы избежать утечки, вызовите `Empty` метод на существующие `CComBSTR` объектов перед их передачей тот адрес, что **[out]** параметра.

Обратите внимание, что тот же код может не привести к утечке в случае параметра функции **[в, out]**.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[Макросы преобразования строк](../atl/reference/string-conversion-macros.md)

