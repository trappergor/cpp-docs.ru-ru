---
title: '> значение &lt;(C++ комментарии к документации)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: de84d1faca59a6c8e4f82fba3605cbd54a05bd2e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988591"
---
# <a name="ltvaluegt"></a>&lt;value&gt;

Тег \<value> позволяет описать свойство и методы доступа к свойству. Обратите внимание, что при добавлении свойства с помощью мастера создания кода из интегрированной среды разработки Visual Studio для нового свойства будет добавлен тег [\<summary>](summary-visual-cpp.md). После этого следует вручную добавить тег \<value> для описания значения, которое представляется свойством.

## <a name="syntax"></a>Синтаксис

```
<value>property-description</value>
```

#### <a name="parameters"></a>Параметры

*property-description*<br/>
Описание свойства.

## <a name="remarks"></a>Заметки

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

```cpp
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

## <a name="see-also"></a>См. также:

[Документация XML](xml-documentation-visual-cpp.md)
