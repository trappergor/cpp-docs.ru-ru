---
title: Класс future_error
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: 2b3f754c0ceb7384d99c6a657de214d30aca24b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430477"
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

**Заголовок:** \<будущих >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Класс logic_error](../standard-library/logic-error-class.md)<br/>
[Класс error_code](../standard-library/error-code-class.md)<br/>
