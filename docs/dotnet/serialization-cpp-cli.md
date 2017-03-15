---
title: "Сериализация (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], сериализация"
  - "управляемого кода [C++], сериализация"
  - "NonSerializedAttribute - класс, управляемые приложения"
  - "SerializableAttribute - класс, управляемые приложения"
  - "сериализация [C++]"
  - "сериализация [C++], сведения о сериализации"
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сериализация (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сериализация \(процесс сохранения состояния объекта или элемента на постоянный носитель\) управляемых классов \(в том числе отдельных полей или свойств\) поддерживается классами <xref:System.SerializableAttribute> и <xref:System.NonSerializedAttribute>.  
  
## Примечания  
 Примените настраиваемый атрибут **SerializableAttribute** к управляемому классу, чтобы сериализовать весь класс, или только к отдельным полям или свойствам, чтобы сериализовать части управляемых классов.  Используйте настраиваемый атрибут **NonSerializedAttribute**, чтобы исключить те или иные поля или свойства управляемого класса из сериализации.  
  
## Пример  
  
### Описание  
 В следующем примере класс `MyClass` \(и свойство `m_nCount`\) помечен как сериализуемый.  При этом свойство `m_nData` не является сериализуемым, как показывает настраиваемый атрибут **NonSerialized**:  
  
### Код  
  
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
  
### Комментарии  
 Обратите внимание, что на оба атрибута можно ссылаться по их "коротким именам" \(**Serializable** и **NonSerialized**\).  См. дополнительные пояснения в разделе [Применение атрибутов](../Topic/Applying%20Attributes.md).  
  
## См. также  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)