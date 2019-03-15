---
title: '&lt;Значение > (C++ комментариев документации)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: c0863b41791254992d16d373328ff6c8a5d6f94f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826633"
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

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

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

[Документация XML](xml-documentation-visual-cpp.md)
