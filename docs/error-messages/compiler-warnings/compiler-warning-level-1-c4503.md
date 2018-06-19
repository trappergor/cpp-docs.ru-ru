---
title: Предупреждение (уровень 1) C4503 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 05/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f60fdb44c5368ccc5c5f089002614332d95a63fe
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255678"
---
# <a name="compiler-warning-level-1-c4503"></a>Предупреждение компилятора (уровень 1) C4503

> "*идентификатор*": длина внутреннего имени превышено, имя усечено

## <a name="remarks"></a>Примечания

Это предупреждение компилятора является устаревшим и не создается в Visual Studio 2017 г. и более поздних версий компиляторов.

Внутреннее имя превышает ограничение компилятора (4096) и был усечен. Чтобы избежать этого предупреждения и усечение, уменьшите число аргументов или длина имени идентификаторов, используемых. Внутренние имена больше, чем ограничение компилятора применяется хэш, которые имеют не опасность того, конфликт имен.

Можно при использовании более старой версии Visual Studio, это предупреждение выдается, если код содержит шаблоны специализированные для шаблонов. Например сопоставление схем (стандартная библиотека C++). В этом случае вы можно определить тип ( **структуры**, например), содержащий схему.

Тем не менее, можно выполнить реструктуризацию кода не.  Можно отправить приложение, создающее C4503, но при появлении ошибки во время ссылку на символ, усеченное, может быть трудно определить тип символа в сообщении об ошибке. Отладка может также быть более сложной; отладчик может иметь difficultly сопоставление имени символа после имени типа. Однако правильность программы, не оказывают влияния усеченное имя.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4503 в компиляторах до Visual Studio 2017 г.:

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

В этом примере показано, как переписать код, чтобы разрешить C4503.

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