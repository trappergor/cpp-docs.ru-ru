---
title: Сериализация (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: 74810328d654787be46794a31d857eb3fd0731ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478147"
---
# <a name="serialization-ccli"></a>Сериализация (C++/CLI)

Сериализация (процесс сохранения состояния объекта или члена на постоянный носитель) управляемых классов (в том числе отдельных полей или свойств) поддерживается <xref:System.SerializableAttribute> и <xref:System.NonSerializedAttribute> классы.

## <a name="remarks"></a>Примечания

Применить **SerializableAttribute** настраиваемого атрибута для управляемого класса, чтобы сериализовать весь класс или только к определенным полям или свойствам для сериализации части управляемого класса. Используйте **NonSerializedAttribute** настраиваемого атрибута для освобождения полей или свойств управляемого класса из сериализации.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере, класс `MyClass` (и свойство `m_nCount`) помечен как сериализуемый. Тем не менее `m_nData` свойство не сериализуется, обозначенный **NonSerialized** настраиваемого атрибута:

### <a name="code"></a>Код

```
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>Комментарии

Обратите внимание, что оба атрибута можно ссылаться с помощью их «короткое имя» (**Serializable** и **NonSerialized**). Далее приведено [применение атрибутов](/dotnet/standard/attributes/applying-attributes).

## <a name="see-also"></a>См. также

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)