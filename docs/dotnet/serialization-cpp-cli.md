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
ms.openlocfilehash: b2dfdcaf1a1f33e89d106d4529ffc9af2d08376b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545165"
---
# <a name="serialization-ccli"></a>Сериализация (C++/CLI)

Сериализация (процесс хранения состояния объекта или элемента на постоянный носитель) управляемых классов (включая отдельные поля или свойства) поддерживается классами <xref:System.SerializableAttribute> и <xref:System.NonSerializedAttribute>.

## <a name="remarks"></a>Примечания

Примените настраиваемый атрибут **SerializableAttribute** к управляемому классу, чтобы сериализовать весь класс или применить его только к конкретным полям или свойствам для сериализации частей управляемого класса. Используйте настраиваемый атрибут **NonSerializedAttribute** , чтобы исключить из сериализации поля или свойства управляемого класса.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере класс `MyClass` (и свойство `m_nCount`) помечается как сериализуемый. Однако свойство `m_nData` не сериализуется, как указано **Несериализованным** пользовательским атрибутом:

### <a name="code"></a>Код

```cpp
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

### <a name="comments"></a>Comments

Обратите внимание, что к обоим атрибутам можно обращаться с помощью «краткого имени» (**сериализуемых** и **несериализуемых**). Это Подробнее объясняется в разделах [применение атрибутов](/dotnet/standard/attributes/applying-attributes).

## <a name="see-also"></a>См. также:

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
