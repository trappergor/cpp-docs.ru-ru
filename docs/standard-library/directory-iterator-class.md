---
title: "Класс directory_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator
- FILESYSTEM/std::experimental::filesystem::directory_iterator::directory_iterator
- FILESYSTEM/std::experimental::filesystem::directory_iterator::increment
- FILESYSTEM/std::experimental::filesystem::directory_iterator::operator=
- FILESYSTEM/std::experimental::filesystem::directory_iterator::operator==
- FILESYSTEM/std::experimental::filesystem::directory_iterator::operator!=
- FILESYSTEM/std::experimental::filesystem::directory_iterator::operator*
- FILESYSTEM/std::experimental::filesystem::directory_iterator::operator->
- FILESYSTEM/std::experimental::filesystem::directory_iterator::operator++
dev_langs:
- C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4eb80d5309a7749c1374d72be16798dbeea33bdc
ms.lasthandoff: 02/24/2017

---
# <a name="directoryiterator-class"></a>Класс directory_iterator
Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге. Для итератора X результатом выражения *X является объект класса directory_entry, являющийся оболочкой для имени файла и известных данных о его состоянии.  
  
 Класс сохраняет объект пути к типу (называемый здесь в целях демонстрации mydir), который представляет имя каталога для упорядочивания, и объект типа directory_entry (называемый здесь myentry), который представляет текущее имя файла в последовательности каталогов. Создаваемый по умолчанию объект типа directory_entry содержит пустой путь mydir и представляет итератор конца последовательности.  
  
 Например, при наличии каталога abc с записями def и ghi, код:  
  
 `for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`  
  
 вызовет метод visit с аргументами path("abc/def") и path("abc/ghi").  
  
 Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class directory_iterator;  
```  
  
## <a name="directoryiteratordirectoryiterator"></a>directory_iterator::directory_iterator  
  
```  
directory_iterator() noexcept;  
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;  
directory_iterator(const directory_iterator&) = default;  
directory_iterator(directory_iterator&&) noexcept = default;  
```  
  
 Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы сохраняют pval в mydir, а затем пытаются открыть и прочитать mydir как каталог. В случае успешного выполнения они сохраняют первое имя файла в каталоге myentry; в противном случае — создают итератор конца последовательности.  
  
 Установленные по умолчанию конструкторы работают корректно.  
  
## <a name="directoryiteratorincrement"></a>directory_iterator::increment  
  
```  
directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 Функция пытается перейти к следующему файлу в каталоге. В случае успешного выполнения она сохраняет имя этого файла в myentry; в противном случае — создает итератор конца последовательности.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator!=  
  
```  
bool operator!=(const directory_iterator& right) const;
```  
  
 Оператор-член возвращает !(*this == right).  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator=  
  
```  
directory_iterator& operator=(const directory_iterator&) = default;  
directory_iterator& operator=(directory_iterator&&) noexcept = default;  
```  
  
 Операторы-члены присваивания по умолчанию работают корректно.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator==  
  
```  
bool operator==(const directory_iterator& right) const;
```  
  
 Оператор-член возвращает значение true, только если оба оператора, *this и right, являются или не являются итераторами конца последовательности.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator*  
  
```  
const directory_entry& operator*() const;
```  
  
 Оператор-член возвращает myentry.  
  
## <a name="directoryiteratoroperator-"></a>directory_iterator::operator->  
  
```  
const directory_entry * operator->() const;
```  
  
 Функция-член возвращает значение &**this.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator++  
  
```  
directory_iterator& operator++();
directory_iterator& operator++(int);
```  
  
 Первая функция-член вызывает метод increment(), а затем возвращает значение *this. Вторая функция-член создает копию объекта, вызывает метод increment(), а затем возвращает копию.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<experimental/filesystem>  
  
 **Пространство имен:** std::experimental::filesystem  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)


