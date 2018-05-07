---
title: Экспортирование классов строки с помощью CStringT | Документы Microsoft
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
ms.openlocfilehash: 7510b1f44f49d17211c71419f4dde5a6e6a78974
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-string-classes-using-cstringt"></a>Экспортирование классов строки с помощью CStringT
В прошлом, являться следствием разработчиков MFC `CString` специализации свои собственные классы строк. В Microsoft Visual C++ .NET (MFC 8.0) [CString](../atl-mfc-shared/using-cstring.md) класс была заменена на класс шаблона с именем [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Эта возможность реализована несколько преимуществ:  
  
-   Это разрешено MFC `CString` проекты класс для использования в ATL без привязки больше статической библиотеки MFC или библиотеки DLL.  
  
-   С помощью нового `CStringT` класс шаблона, можно настроить `CString` поведения с помощью шаблона параметров, задающих признаки символа, аналогично шаблоны в стандартной библиотеке C++.  
  
-   При экспорте строки класса из библиотеки DLL с помощью `CStringT`, компилятор автоматически экспортирует `CString` базового класса. Поскольку `CString` сам является классом шаблона, он может создаваться компилятором при использовании, если компилятор учитывает, `CString` импортирован из библиотеки DLL. Если вы перенесли проекты Visual C++ 6.0 до Visual C++ .NET, вы может увидеть ошибках компоновщика символ для многозначного `CString` из-за конфликта `CString` импортирована из библиотеки DLL и версии локальные экземпляры. Ниже описан правильный способ сделать это. Дополнительные сведения об этой проблеме см. в статье базы знаний «компоновка ошибок при импорте CString производные классы» (номер Q309801) в [ http://support.microsoft.com/default.aspx ](http://support.microsoft.com/default.aspx).  
  
 Следующий сценарий вызовет компоновщик для создания ошибки символ для многократно определенных классов. Предположим, что вы экспортируете `CString`-производного класса (`CMyString`) из библиотеки DLL расширения MFC:  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]  
  
 Код объекта-получателя используется сочетание `CString` и `CMyString`. «MyString.h» не включен в предкомпилированный заголовок, а также использование некоторых `CString` не имеет `CMyString` видимым.  
  
 Предположим, что в параметре `CString` и `CMyString` классов в отдельным файлам исходного кода, Source1.cpp и Source2.cpp. Используется в Source1.cpp, `CMyString` и #include MyString.h. Используется в Source2.cpp, `CString`, но это не так #include MyString.h. В этом случае компоновщик выдаст ошибку, о `CStringT` определен несколько раз. Причиной этого является `CString` , оба импортирована из библиотеки DLL, которая экспортирует `CMyString`и создаются локально с помощью компилятора через `CStringT` шаблона.  
  
 Чтобы устранить эту проблему, выполните следующие действия.  
  
 Экспорт `CStringA` и `CStringW` (и необходимые базовых классов) из MFC90. БИБЛИОТЕКИ DLL. Проекты, которые включают MFC использует только экспорта библиотеки DLL MFC `CStringA` и `CStringW`, как показано в предыдущих реализациях MFC.  
  
 Затем создайте экспортируемый производного класса с помощью `CStringT` шаблона, как `CStringT_Exported` меньше, например:  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]  
  
 В AfxStr.h, замените предыдущий `CString`, `CStringA`, и `CStringW` определения типов, как показано ниже:  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]  
  
 Существует несколько проблем:  
  
-   Не следует экспортировать `CStringT` себя так, как это приведет к ATL-проекты, доступные только для экспорта специализированный `CStringT` класса.  
  
-   С помощью экспортируемый производный класс от `CStringT` сводит к минимуму необходимость повторной реализации `CStringT` функциональные возможности. Дополнительный код ограничена пересылки конструкторов, чтобы `CStringT` базового класса.  
  
-   `CString`, `CStringA`, и `CStringW` только должен быть помечен как `__declspec(dllexport/dllimport)` при построении с MFC библиотеки DLL "Общие". Если связывание с статические библиотеки MFC, должны не помечать эти классы, как экспортировать; в противном случае — внутренняя использование `CString`, `CStringA`, и `CStringW` внутри отметит пользователя библиотеки DLL `CString` также экспортировать.  
  
## <a name="related-topics"></a>См. также  
 [Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
  
## <a name="see-also"></a>См. также  
 [С помощью CStringT](../atl-mfc-shared/using-cstringt.md)   
 [Использование CString](../atl-mfc-shared/using-cstring.md)

