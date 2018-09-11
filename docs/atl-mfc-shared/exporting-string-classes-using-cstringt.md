---
title: Экспорт строковых классов с помощью CStringT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7a4e033ac940d414cb3ece11dfd927b8c2658f7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762565"
---
# <a name="exporting-string-classes-using-cstringt"></a>Экспорт строковых классов с помощью CStringT

В прошлом, разработчикам MFC производного от `CString` специализации свои собственные классы строк. В Microsoft Visual C++ .NET (MFC 8.0) [CString](../atl-mfc-shared/using-cstring.md) класс был заменен классом шаблона с именем [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Это обеспечило несколько преимуществ:

- Это разрешено MFC `CString` класс для использования в ATL проекты без компоновки в больше статической библиотеки MFC или библиотеки DLL.

- С новым `CStringT` класс шаблона, вы можете настроить `CString` поведения с помощью шаблона параметров, задающих признаки символов, аналогичные шаблоны в стандартной библиотеке C++.

- При экспорте свой собственный класс строку из DLL с помощью `CStringT`, компилятор автоматически экспортирует `CString` базового класса. Так как `CString` сам является классом шаблона, он может быть создан компилятором при использовании, если компилятор учитывает, `CString` импортируется из библиотеки DLL. Если вы перенесли проекты Visual C++ 6.0 в Visual C++ .NET, можно увидеть ошибки компоновщика символ для многозначного `CString` из-за конфликта `CString` импортирована из библиотеки DLL и локальные экземпляры версии. Ниже описан правильный способ это сделать. Дополнительные сведения об этой проблеме см. в статье базы знаний, «связывание ошибки при импорте CString производные классы» (номер Q309801) в [ http://support.microsoft.com/default.aspx ](http://support.microsoft.com/default.aspx).

Следующий сценарий приведет к компоновщику приводить к ошибкам символ для multiply определенных классов. Предположим, что при экспорте `CString`-производный класс (`CMyString`) из библиотеки DLL расширения MFC:

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

Код потребителя использует сочетание `CString` и `CMyString`. «MyString.h» не включен в предкомпилированный заголовок и некоторые использование `CString` имеет `CMyString` видимым.

Предположим, что `CString` и `CMyString` классы в отдельных исходных файлах, Source1.cpp и Source2.cpp. В Source1.cpp, используется `CMyString` и #include MyString.h. В Source2.cpp, используется `CString`, но не #include MyString.h. В этом случае компоновщик пожалуется об `CStringT` определен несколько раз. Это вызвано `CString` , импортированы из библиотеки DLL, которая экспортирует `CMyString`и создаются локально с помощью компилятора через `CStringT` шаблона.

Чтобы устранить эту проблему, сделайте следующее:

Экспорт `CStringA` и `CStringW` (и необходимые базовые классы) из MFC90. БИБЛИОТЕКА DLL. Проекты, которые включают MFC всегда будет использовать экспорта библиотеки DLL MFC `CStringA` и `CStringW`, как показано в предыдущих реализациях MFC.

Затем создайте экспортируемый производного класса с помощью `CStringT` шаблона, как `CStringT_Exported` меньше, например:

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

В AfxStr.h, замените предыдущий `CString`, `CStringA`, и `CStringW` определения типов, как показано ниже:

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

Существует несколько моментов.

- Не следует экспортировать `CStringT` самой, так как это приведет к ATL-проекты, доступные только для экспорта специализированный `CStringT` класса.

- С помощью экспортируемый производный класс от `CStringT` сводит к минимуму необходимость повторной реализации `CStringT` функциональные возможности. Дополнительный код ограничивается пересылки конструкторы `CStringT` базового класса.

- `CString`, `CStringA`, и `CStringW` только должен быть помечен как `__declspec(dllexport/dllimport)` при построении с помощью MFC общие библиотеки DLL. Если связывание с статические библиотеки MFC, должны не помечать эти классы, как экспортировать; в противном случае внутренняя использование `CString`, `CStringA`, и `CStringW` внутри пометит пользователя библиотеки DLL `CString` как также экспорту.

## <a name="related-topics"></a>См. также

[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>См. также

[С помощью CStringT](../atl-mfc-shared/using-cstringt.md)   
[Использование CString](../atl-mfc-shared/using-cstring.md)

