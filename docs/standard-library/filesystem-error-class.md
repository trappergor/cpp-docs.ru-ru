---
title: Класс filesystem_error | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1acf34f8478bc075b53780f1e48df125c22608b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="filesystemerror-class"></a>Класс filesystem_error

Базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.

## <a name="syntax"></a>Синтаксис

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Примечания

Этот класс служит базовым классом для всех исключений, уведомляющих об ошибке в функциях \<filesystem>. Он хранит объект типа string (называемый здесь mymesg в целях демонстрации). Он также хранит два объекта типа path, называемые mypval1 и mypval2.

## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

Первый конструктор создает сообщение из what_arg и ec. Второй конструктор также создает сообщение из pval1, которое он сохраняет в mypval1. Третий конструктор также создает сообщение из pval1, которое он сохраняет в mypval1, и из pval2, которое он сохраняет в mypval2.

## <a name="filesystemerrorpath1"></a>filesystem_error::path1

```cpp
const path& path1() const noexcept;
```

Функция-член возвращает значение mypval1.

## <a name="filesystemerrorpath2"></a>filesystem_error::path2

```cpp
const path& path2() const noexcept;
```

Функция-член возвращает значение mypval2.

## <a name="filesystemerrorwhat"></a>filesystem_error::what

```cpp
const char *what() const noexcept;
```

Функция-член возвращает указатель на строку NTBS, предпочтительно состоящую из runtime_error::what(), system_error::what(), mymesg, mypval1.native_string() и mypval2.native_string().

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental::filesystem

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Класс system_error](../standard-library/system-error-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
