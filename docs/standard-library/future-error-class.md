---
title: Класс future_error
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: ed3f9d63c45d0e185e3e1476094736d132822173
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447345"
---
# <a name="futureerror-class"></a>Класс future_error

Описывает объект исключения, который можно вызывать методами типов, управляющих объектами [future](../standard-library/future-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>Требования

**Заголовок:** \<будущие >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Класс logic_error](../standard-library/logic-error-class.md)\
[Класс error_code](../standard-library/error-code-class.md)
