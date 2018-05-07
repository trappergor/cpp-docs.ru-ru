---
title: Взаимный импорт | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- mutual DLL imports [C++]
- AFX_DATA
- importing DLLs [C++], mutual imports
- mutually importing executable files [C++]
- AFX_EXT_CLASS macro
- circular imports
- _AFXEXT preprocessor symbol
- DLLs [C++], importing
- executable files [C++], importing
- extension DLLs [C++], mutual imports
- exporting DLLs [C++], mutual imports
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b43977f86be409698d8fbdba16fc63d85acfac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="mutual-imports"></a>Взаимный импорт
Экспорт или импорт другого исполняемого файла представляет затруднения, если импорт является взаимным (или циклическим). Например две библиотеки DLL импортировать символы друг от друга, аналогично взаимно рекурсивные функции.  
  
 Проблема с взаимное импортирование исполняемых файлов (обычно DLL) — ни можно создать без построен другой. Каждый процесс построения требует в качестве входного, библиотеку импорта, созданные в процессе построения.  
  
 Решением является использование программы LIB с параметром/DEF, который создает библиотеку импорта без построения исполняемого файла. Эта программа построение библиотеки импорта, требуется, независимо от того, сколько библиотек DLL связанных или насколько сложны, зависимости.  
  
 — Общее решение для разрешения взаимного импорта:  
  
1.  Поочередно каждой библиотеки DLL. (Любое заказа — возможно, хотя некоторые последовательности более оптимального). Если все необходимые библиотеки импорта существуют и являются устаревшими, запустите программу LINK для построения исполняемого файла (DLL). Это создает библиотеку импорта. В противном случае запустите программу LIB для создания библиотеки импорта.  
  
     Запуск программы LIB с параметром/DEF создает дополнительный файл с. Расширение EXP. . EXP-файл должен использоваться позже для создания исполняемого файла.  
  
2.  После использования LINK или LIB для построения всех библиотек импорта, вернитесь и выполните программу LINK для построения всех исполняемых файлов, которые не были построены на предыдущем шаге. Обратите внимание, что соответствующий EXP-файл должно быть указано в строке ССЫЛОК.  
  
     Если ранее утилита LIB создает библиотеку импорта для DLL1 раньше выполнялся, LIB бы получен файл DLL1.exp также. При построении DLL1.dlll, необходимо использовать DLL1.exp в качестве входного для СВЯЗИ.  
  
 На следующем рисунке решения для двух взаимного импорта библиотеки DLL, DLL1 и DLL2. Шаг 1 является запуск LIB, с установленным параметром/DEF, на DLL1. Шаг 1 создает DLL1.lib библиотеки импорта и DLL1.exp. На шаге 2 библиотека импорта используется для построения DLL2, который в свою очередь создает библиотеку импорта для DLL2 символов. Шаг 3 построение DLL1 с помощью DLL1.exp и DLL2.lib в качестве входных данных. Обратите внимание, что файл EXP для DLL2 не является необходимым, поскольку LIB не используется для построения DLL2 библиотеки импорта.  
  
 ![Компоновка двух библиотек DLL с помощью взаимного импорта](../build/media/vc37yj1.gif "vc37YJ1")  
Компоновка двух библиотек DLL с взаимный импорт  
  
## <a name="limitations-of-afxext"></a>Ограничения _AFXEXT  
 Можно использовать `_AFXEXT` символ препроцессора для библиотек, при условии, что у вас несколько слоев расширения MFC DLL расширения MFC. При наличии расширения MFC DLL-библиотеки, которые вызывают или являются производными от классов в собственное расширение MFC библиотеки DLL, которые являются производными от классов MFC, необходимо использовать собственную препроцессора во избежание неоднозначности.  
  
 Проблема в том, что в Win32, необходимо явно объявить все данные в виде **__declspec(dllexport)** если экспорт из библиотеки DLL, и **__declspec(dllimport)** при импорте из библиотеки DLL. При определении `_AFXEXT`, заголовки MFC убедитесь, что **AFX_EXT_CLASS** правильно определен.  
  
 Если имеется несколько слоев, один символ например **AFX_EXT_CLASS** недостаточно, так как расширение MFC DLL может экспортировать новые классы, а также импортировать другие классы из другой Библиотеки расширения MFC. Чтобы решить эту проблему, используйте специальный символ препроцессора, указывающее, вы создаете самой библиотеки DLL и использование библиотеки DLL. Например представьте двух библиотек DLL расширения MFC, A.dll и B.dll. Каждая из них экспортирует некоторые классы в файлах A.h и B.h соответственно. B.dll использует классы из A.dll. Файлы заголовков будет выглядеть примерно следующим образом:  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A   __declspec(dllexport)  
#else  
   #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
  
// B.H  
#ifdef B_IMPL  
   #define CLASS_DECL_B   __declspec(dllexport)  
#else  
   #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition ... };  
...  
```  
  
 При построении A.dll построены с `/D A_IMPL` и при построении B.dll, он создается с `/D B_IMPL`. С помощью отдельных символов для каждой библиотеки DLL `CExampleB` экспортируется и `CExampleA` импортируется при построении B.dll. `CExampleA` экспортируется при построении A.dll и импортируется, когда он используется библиотекой B.dll (или другим клиентом).  
  
 Такой тип архитектуры не может выполняться при использовании встроенной **AFX_EXT_CLASS** и `_AFXEXT` символы препроцессора. Способ, описанный выше решает эту проблему способом, отличным от используется классами MFC при построении его Active технологии, базы данных и библиотек DLL расширения MFC сети.  
  
## <a name="not-exporting-the-entire-class"></a>Экспортирует весь класс  
 Если не экспортируется весь класс, необходимо убедиться, корректно экспортированы элементы необходимые данные, создаваемые макросами MFC. Это можно сделать путем переопределения `AFX_DATA` макрос определенного класса. Это следует делать каждый раз, не экспортируется весь класс.  
  
 Пример:  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A  _declspec(dllexport)  
#else  
   #define CLASS_DECL_A  _declspec(dllimport)  
#endif  
  
#undef  AFX_DATA  
#define AFX_DATA CLASS_DECL_A  
  
class CExampleA : public CObject  
{  
   DECLARE_DYNAMIC()  
   CLASS_DECL_A int SomeFunction();  
   //... class definition ...  
};  
  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)  
  
-   [Экспорт из библиотеки DLL с помощью. DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C++ для использования в реализации языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Служебная программа LIB и параметр/DEF](../build/reference/lib-reference.md)  
  
## <a name="see-also"></a>См. также  
 [Импортирование и экспортирование](../build/importing-and-exporting.md)