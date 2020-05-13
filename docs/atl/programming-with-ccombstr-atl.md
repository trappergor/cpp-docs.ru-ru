---
title: Программирование с использованием CComBSTR (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 020c2d18c721e658d15bb1451039154ae50b99f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321797"
---
# <a name="programming-with-ccombstr-atl"></a>Программирование с использованием CComBSTR (ATL)

Класс ATL [CComBSTR](../atl/reference/ccombstr-class.md) обеспечивает обертку вокруг типа данных BSTR. Хотя `CComBSTR` это полезный инструмент, Есть несколько ситуаций, которые требуют осторожности.

- [Проблемы преобразования](#programmingwithccombstr_conversionissues)

- [Проблемы с областью действия](#programmingwithccombstr_scopeissues)

- [Явное освобождение объекта CComBSTR](#programmingwithccombstr_explicitlyfreeing)

- [Использование объектов CComBSTR в петлях](#programmingwithccombstr_usingloops)

- [Проблемы утечки памяти](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a>Проблемы преобразования

Хотя `CComBSTR` несколько методов автоматически преобразуют аргумент строки ANSI в Unicode, методы всегда возвращают строки формата Unicode. Чтобы преобразовать строку вывода обратно в ANSI, используйте класс преобразования ATL. Для получения дополнительной информации о [ATL and MFC String Conversion Macros](reference/string-conversion-macros.md)классах конверсии ATL см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

Если вы используете строку буквально `CComBSTR` для изменения объекта, используйте широкие строки символов. Это уменьшит ненужные конверсии.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a>Проблемы с областью действия

Как и в случае с `CComBSTR` любым хорошо себя классом, освободит свои ресурсы, когда он выйдет за рамки. Если функция возвращает указатель `CComBSTR` в строку, это может вызвать проблемы, так как указатель будет ссылаться на память, которая уже была освобождена. В этих случаях `Copy` используйте метод, как показано ниже.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a>Явное освобождение объекта CComBSTR

Можно явно освободить строку, содержащуюся в объекте, `CComBSTR` прежде чем объект выходит области. Если строка освобождена, `CComBSTR` объект становится недействительным.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a>Использование объектов CComBSTR в петлях

Поскольку `CComBSTR` класс выделяет буфер для выполнения определенных `+=` операций, таких как оператор или `Append` метод, не рекомендуется выполнять манипуляции строками внутри плотного цикла. В таких `CStringT` ситуациях обеспечивает более высокую производительность.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a>Проблемы утечки памяти

Передача адреса инициализированного `CComBSTR` функции в качестве параметра приводит к утечке памяти. **[out]**

В приведенном ниже примере строка, выделенная для удержания строки, `"Initialized"` протекает при замене функции. `MyGoodFunction`

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

Чтобы избежать утечки, `Empty` позвоните `CComBSTR` методу на существующие объекты, прежде чем передать адрес **в** качестве параметра.

Обратите внимание, что тот же код не приведет к утечке, если параметр функции был **«в, вне».**

## <a name="see-also"></a>См. также раздел

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[Струнная конверсия Макрос](../atl/reference/string-conversion-macros.md)
