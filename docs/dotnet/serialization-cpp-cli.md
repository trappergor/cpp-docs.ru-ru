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
ms.openlocfilehash: 794a71ae9a146b691ba6a4377a7fdf2c3ddd3501
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384677"
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
