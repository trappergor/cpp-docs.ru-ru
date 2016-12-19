---
title: "Класс HString | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString"
dev_langs: 
  - "C++"
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс HString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Обеспечивает поддержку манипулирования дескрипторами HSTRING.  
  
## Синтаксис  
  
```cpp  
class HString;  
```  
  
## Примечания  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] предоставляет доступ к строкам посредством дескрипторов HSTRING.  Класс HString предоставляет удобные функции и операторы для упрощения использования дескрипторов HSTRING.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор HString::HString](../windows/hstring-hstring-constructor.md)|Инициализирует новый экземпляр класса HString.|  
|[Деструктор HString::~HString](../windows/hstring-tilde-hstring-destructor.md)|Ликвидирует текущий экземпляр класса HString.|  
  
### Члены  
  
|Name|Описание|  
|----------|--------------|  
|[Метод HString::Set](../Topic/HString::Set%20Method.md)|Устанавливает значение текущего объекта HString равным указанной двухбайтовой строке или параметру HString.|  
|[Метод HString::Attach](../windows/hstring-attach-method.md)|Связывает указанный объект HString с текущим объектом HString.|  
|[Метод HString::CopyTo](../windows/hstring-copyto-method.md)|Копирует текущий объект HString в объект HSTRING.|  
|[Метод HString::Detach](../Topic/HString::Detach%20Method.md)|Отменяет связь указанного объекта HString с его базовым значением.|  
|[Метод HString::GetAddressOf](../windows/hstring-getaddressof-method.md)|Извлекает указатель на базовый дескриптор HSTRING.|  
|[Метод HString::Get](../Topic/HString::Get%20Method.md)|Извлекает значение базового дескриптора HSTRING.|  
|[Метод HString::Release](../windows/hstring-release-method.md)|Удаляет базовое строковое значение и инициализирует текущий объект HString пустым значением.|  
|[Метод HString::MakeReference](../Topic/HString::MakeReference%20Method.md)|Создает объект HStringReference из указанного строкового параметра.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор HString::Operator\=](../Topic/HString::Operator=%20Operator.md)|Перемещает значение другого объекта HString в текущий объект HString.|  
|[Оператор HString::Operator\=\=](../windows/hstring-operator-equality-operator.md)|Указывает, действительно ли два параметра равны.|  
|[Оператор HString::Operator\!\=](../windows/hstring-operator-inequality-operator.md)|Указывает, действительно ли два параметра не равны.|  
  
## Иерархия наследования  
 `HString`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)