---
title: "&lt;filesystem&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
dev_langs:
- C++
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 4cb454ca6ea92ede5c4cf83c1072e22e60577811
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltfilesystemgt"></a>&lt;filesystem&gt;
Чтобы иметь доступ к классам и функциям, позволяющим управлять и получать сведения о путях, файлах и каталогах, включите заголовок \<filesystem>.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <experimental/filesystem> // C++-standard header file name  
#include <filesystem> // Microsoft-specific implementation header file name  
using namespace std::experimental::filesystem::v1;  
```  
  
> [!IMPORTANT]
>  На момент выпуска Visual Studio 2017 заголовок \<experimental/filesystem> еще не был стандартом C++. Visual C++ 2017 реализует окончательный проект стандарта, который находится в [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf).  
  
 Этот заголовок поддерживает файловые системы одного из двух широких классов операционных систем размещения: Microsoft Windows и Posix.  
  
 Хотя большинство функций являются общими для обеих операционных систем, в этом документе указываются некоторые отличия. Например:  
  
-   Windows поддерживает несколько корневых имен, таких как c: или \\\network_name. Поэтому файловая система состоит из леса деревьев, где каждое дерево имеет свой собственный корневой каталог (например, c:\ или \\\network_name\\) и свой собственный текущий каталог для завершения относительного пути (который не является абсолютным путем).  
  
-   Posix поддерживает одно дерево без корневого имени, единый корневой каталог/ и один текущий каталог.  
  
 Другое важное отличие состоит в представлении путей:  
  
-   Windows использует завершающуюся нулем последовательность символов wchar_t в кодировке UTF-16 (один или два элемента для каждого символа).  
  
-   Posix использует завершающуюся нулем последовательность символов char в кодировке UTF-8 (один или несколько элементов для каждого символа).  
  
-   В объекте класса path хранится путь в собственном формате, однако поддерживается простое преобразование между этим хранимым форматом и различными внешними:  
  
    -   Завершающаяся нулем последовательность символов char в кодировке, предпочитаемой в операционной системе.  
  
    -   Завершающаяся нулем последовательность символов char в кодировке UTF-8.  
  
    -   Завершающаяся нулем последовательность символов wchar_t в кодировке, предпочитаемой в операционной системе.  
  
    -   Завершающаяся нулем последовательность символов char16_t в кодировке UTF-16.  
  
    -   Завершающаяся нулем последовательность символов char32_t в кодировке UTF-32.  
  
 Взаимные преобразования между этими представлениями выполняются по мере необходимости с помощью одного или нескольких аспектов `codecvt`. Если конкретный языковой стандарт не назначен, эти аспекты поступают из глобального языкового стандарта.  
  
 Еще одно различие заключается в степени детализации, с которой каждая операционная система позволяет указать разрешения доступа к файлу или каталогу.  
  
1.  Windows регистрирует сведения о том, доступен ли файл только для чтения или для записи, — атрибут, который не имеет смысла для каталогов.  
  
2.  Posix регистрирует сведения о том, доступен ли файл для чтения, записи или выполнения (просмотра, если это каталог) владельцем, группой владельцев или любым пользователем (плюс несколько других разрешений).  
  
 Общей характеристикой обеих систем является структура, применяемая к пути после корневого имени. Для пути c:/abc/xyz/def.ext  
  
-   Корневое имя — c:.  
  
-   Корневой каталог — /.  
  
-   Корневой путь — c:/.  
  
-   Относительный путь — abc/xyz/def.ext.  
  
-   Родительский путь — c:/abc/xyz.  
  
-   Имя файла — def.ext.  
  
-   Основа — def.  
  
-   Расширение — .ext.  
  
 Небольшое отличие заключается в **предпочтительном разделителе**между последовательностью каталогов в пути. Обе операционные системы позволяют записывать прямую косую черту (/), но в некоторых контекстах Windows предпочитает обратную косую черту (\\).  
  
 Наконец, важная особенность объектов path состоит в том, что их можно использовать, когда в классах, определенных в заголовке \<fstream>, требуется аргумент filename.  
  
 Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс directory_entry](../standard-library/directory-entry-class.md)|Описывает объект, возвращаемый `directory_iterator` или `recursive_directory_iterator`, и содержит путь.|  
|[Класс directory_iterator](../standard-library/directory-iterator-class.md)|Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге файловой системы.|  
|[Класс filesystem_error](../standard-library/filesystem-error-class.md)|Базовый класс для исключений, создаваемых для отчета о переполнении системы низкого уровня.|  
|[Класс path](../standard-library/path-class.md)|Определяет класс, который хранит объект типа шаблона `String` , пригодный для использования в качестве имени файла.|  
|[Класс recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)|Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге файловой системы. Итератор может также просматривать подкаталоги.|  
|[Класс file_status](../standard-library/file-status-class.md)|Создает оболочку для `file_type`.|  
  
## <a name="structs"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура space_info](../standard-library/space-info-structure.md)|Содержит сведения о томе.|  
  
## <a name="functions"></a>Функции  
 [функции \<filesystem>](../standard-library/filesystem-functions.md)  
  
## <a name="operators"></a>Операторы  
 [операторы \<filesystem>](../standard-library/filesystem-operators.md)  
  
## <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|Перечисление, используемое с функцией [copy_file](http://msdn.microsoft.com/en-us/4af7a9b0-8861-45ed-b84e-0307f0669d60) , которое определяет действия в случае, если целевой файл уже существует.|  
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|Перечисление, указывающее параметры итераторов каталога.|  
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|Перечисление для типов файлов.|  
|[perms](../standard-library/filesystem-enumerations.md#perms)|Тип битовой маски, используемый для передачи разрешений и параметров для разрешений.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)




