---
title: "Класс recursive_directory_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c432cde8a4c565e6195658ab27ce5f2cb1838f6a
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="recursivedirectoryiterator-class"></a>Класс recursive_directory_iterator
Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге, возможно, рекурсивно просматривая подкаталоги. Для итератора X результатом выражения *X является объект класса directory_entry, являющийся оболочкой для имени файла и известных данных о его состоянии.  
  
 Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class recursive_directory_iterator;  
```  
  
## <a name="remarks"></a>Примечания  
 Шаблон класса хранит:  
  
1.  объект типа stack<pair\<directory_iterator, path>> (называемый здесь mystack в целях демонстрации), который представляет вложенные каталоги для упорядочивания;  
  
2.  объект типа directory_entry (называемый здесь myentry), который представляет имя текущего файла в последовательности каталогов;  
  
3.  объект типа bool (называемый здесь no_push), который записывает, отключен ли рекурсивный спуск в подкаталоги;  
  
4.  объект типа directory_options (называемый здесь myoptions), который записывает параметры, установленные при создании.  
  
 Созданный по умолчанию объект типа recursive_directory_entry содержит итератор конца последовательности в mystack.top().first и представляет итератор конца последовательности. Например, при наличии каталога abc с записями def (каталог), def/ghi и jkl код  
  
```  
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)  
    visit(next->path());
```  
  
 вызывает метод visit с аргументами `path("abc/def/ghi") and path("abc/jkl").`. Определить перебор в поддереве каталога можно двумя способами:  
  
1.  Символьная ссылка каталога будет проверяться только в том случае, если recursive_directory_iterator создается с аргументом directory_options, значением которого является directory_options::follow_directory_symlink.  
  
2.  Если вызвать функцию disable_recursion_pending, то рекурсивная проверка следующего каталога, обнаруженного во время приращения, выполняться не будет.  
  
## <a name="recursivedirectoryiteratordepth"></a>recursive_directory_iterator::depth  
  
```  
int depth() const;
```  
  
 Возвращает mystack.size() - 1, поэтому pval находится на нулевой глубине.  
  
## <a name="recursivedirectoryiteratordisablerecursionpending"></a>recursive_directory_iterator::disable_recursion_pending  
  
```  
void disable_recursion_pending();
```  
  
 Функция-член сохраняет значение true в объект no_push.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator!=  
  
```  
bool operator!=(const recursive_directory_iterator& right) const;
```  
  
 Оператор-член возвращает !(*this == right).  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator=  
  
```  
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;  
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;  
```  
  
 Операторы-члены присваивания по умолчанию работают корректно.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator==  
  
```  
bool operator==(const recursive_directory_iterator& right) const;
```  
  
 Оператор-член возвращает значение true, только если оба оператора, *this и right, являются или не являются итераторами конца последовательности.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator*  
  
```  
const directory_entry& operator*() const;
```  
  
 Оператор-член возвращает myentry.  
  
## <a name="recursivedirectoryiteratoroperator-"></a>recursive_directory_iterator::operator->  
  
```  
const directory_entry * operator->() const;
```  
  
 Возвращает &\*\*this.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator++  
  
```  
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```  
  
 Первая функция-член вызывает метод increment(), а затем возвращает значение *this. Вторая функция-член создает копию объекта, вызывает метод increment(), а затем возвращает копию.  
  
## <a name="recursivedirectoryiteratoroptions"></a>recursive_directory_iterator::options  
  
```  
directory_options options() const;
```  
  
 Возвращает myoptions.  
  
## <a name="recursivedirectoryiteratorpop"></a>recursive_directory_iterator::pop  
  
```  
void pop();
```  
  
 Если depth() == 0 объект становится итератором конца последовательности. В противном случае функция-член завершает проверку текущего (самого глубокого) каталога и возобновляет ее на следующем нижнем уровне глубины.  
  
## <a name="recursivedirectoryiteratorrecursionpending"></a>recursive_directory_iterator::recursion_pending  
  
```  
bool recursion_pending() const;
```  
  
 Возвращает !no_push.  
  
## <a name="recursivedirectoryiteratorrecursivedirectoryiterator"></a>recursive_directory_iterator::recursive_directory_iterator  
  
```  
recursive_directory_iterator() noexcept;  
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const path& pval,  
    directory_options opts);

recursive_directory_iterator(const path& pval,  
    directory_options opts,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const recursive_directory_iterator&) = default;  
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;  
```  
  
 Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы сохраняют значение false в no_push и directory_options::none в myoptions, а затем пытаются открыть и прочитать pval как каталог. В случае успешного выполнения они инициализируют mystack и myentry для обозначения первого имени файла, не являющегося каталогом, во вложенной последовательности; в противном случае — создают итератор конца последовательности.  
  
 Четвертый и пятый конструкторы работают так же, как второй и третий, за исключением того, что сначала сохраняют opts в myoptions. Установленные по умолчанию конструкторы работают корректно.  
  
## <a name="recursivedirectoryiteratorincrement"></a>recursive_directory_iterator::increment  
  
```  
recursive_directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 Функция пытается перейти к имени следующего файла во вложенной последовательности. В случае успешного выполнения она сохраняет имя этого файла в myentry; в противном случае — создает итератор конца последовательности.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<filesystem >  
  
 **Пространство имен:** std::tr2::sys  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)

