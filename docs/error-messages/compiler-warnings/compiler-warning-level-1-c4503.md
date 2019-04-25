---
title: Предупреждение компилятора (уровень 1) C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 94c88511d87c3adf3cf5687a94948c83ebc5b3d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160982"
---
# <a name="compiler-warning-level-1-c4503"></a>Предупреждение компилятора (уровень 1) C4503

> "*идентификатор*": длина внутреннего имени превышено, имя усечено

## <a name="remarks"></a>Примечания

Предупреждения компилятора является устаревшим и не создается в Visual Studio 2017 и более поздние версии компиляторов.

Декорированное имя превышает ограничение компилятора (4096) и была усечена. Чтобы избежать этого предупреждения и усечение, уменьшите число аргументов или имя длин идентификаторы, используемые. Декорированные имена, которые являются больше, чем ограничение компилятора хэш применен и не существует риск конфликта имен.

Можно при использовании более ранней версии Visual Studio, это предупреждение, если код содержит шаблоны специализированные для шаблонов. Например сопоставление схем (стандартная библиотека C++). В этом случае вы можно определить тип ( **структуры**, например), содержащей карту.

Тем не менее, можно выполнить не реструктуризацию кода.  Можно отправить в приложение, которое создает C4503, но если возникают ошибки времени ссылку на символ, усеченное, может быть трудно определить тип символа в ошибку. Отладка может также быть более сложным; отладчик может иметь оптимизирована сопоставления имени символа имени типа. Правильность работы программы, однако это не влияет, усеченное имя.

## <a name="example"></a>Пример

В следующем примере возникает предупреждение C4503 в компиляторов c до Visual Studio 2017:

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

В этом примере показан один из способов переписки устранения C4503:

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```