---
title: '&lt;value&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: 84a19c96e3e7024dbb891c6bde91646d4731b2be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599294"
---
# <a name="ltvaluegt-visual-c"></a>&lt;value&gt; (Visual C++)

Тег \<value> позволяет описать свойство и методы доступа к свойству. Обратите внимание, что при добавлении свойства с помощью мастера создания кода из интегрированной среды разработки Visual Studio для нового свойства будет добавлен тег [\<summary>](../ide/summary-visual-cpp.md). После этого следует вручную добавить тег \<value> для описания значения, которое представляется свойством.

## <a name="syntax"></a>Синтаксис

```
<value>property-description</value>
```

#### <a name="parameters"></a>Параметры

*property-description*<br/>
Описание свойства.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

```
// xml_value_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_value_tag.dll
using namespace System;
/// Text for class Employee.
public ref class Employee {
private:
   String ^ name;
   /// <value>Name accesses the value of the name data member</value>
public:
   property String ^ Name {
      String ^ get() {
         return name;
      }
      void set(String ^ i) {
         name = i;
      }
   }
};
```

## <a name="see-also"></a>См. также

[Документация XML](../ide/xml-documentation-visual-cpp.md)