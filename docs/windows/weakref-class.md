---
title: "Класс WeakRef | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef - класс"
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс WeakRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет собой *слабую ссылку*, которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.  
  
## Синтаксис  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## Примечания  
 Объект WeakRef поддерживает *строгую ссылку*, которая связана с объектом и может быть допустимой или недопустимой. Вызовите метод As\(\) или AsIID\(\), чтобы получить строгую ссылку. Когда строгая ссылка допустима, возможно обращение к связанному объекту. Когда строгая ссылка недопустима \(`nullptr`\), связанный объект недоступен.  
  
 Объект WeakRef обычно используется для представления объекта, существованием которого управляет внешний поток или приложение. Например, создайте объект WeakRef из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.  
  
 Обратите внимание на изменение в поведении методов [As](../windows/weakref-as-method.md), [AsIID](../windows/weakref-asiid-method.md) и [CopyTo](../windows/weakref-copyto-method.md) в пакете SDK для Windows 10. Ранее после вызова любого из этих методов можно было проверить `nullptr` для WeakRef, чтобы узнать, были ли строгая ссылка успешно получена, как в следующем коде:  
  
```cpp  
WeakRef wr; strongComptrRef.AsWeak(&wr); // Now suppose that the object strongComPtrRef points to no longer exists // and the following code tries to get a strong ref from the weak ref: ComPtr<ISomeInterface> strongRef; HRESULT hr = wr.As(&strongRef); // This check won't work with the Windows 10 SDK version of the library. // Use the HRESULT from previous As() call instead. if(wr == nullptr) { wprintf(L"Couldn’t get strong ref!"); }  
  
```  
  
 Приведенный выше код не работает при использовании пакета SDK для Windows 10 \(или более поздней версии\). Вместо этого проверьте значение HRESULT, возвращенное методом As или AsIID, или указатель, переданный для `nullptr`.  
  
```cpp  
if (hr != S_OK) { wprintf(L"Couldn't get strong ref!"); }  
  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор WeakRef::WeakRef](../windows/weakref-weakref-constructor.md)|Инициализирует новый экземпляр класса WeakRef.|  
|[Деструктор WeakRef::~WeakRef](../windows/weakref-tilde-weakref-destructor.md)|Деинициализирует текущий экземпляр класса WeakRef.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод WeakRef::As](../windows/weakref-as-method.md)|Задает определенный указатель ComPtr для представления указанного интерфейса.|  
|[Метод WeakRef::AsIID](../windows/weakref-asiid-method.md)|Задает определенный указатель ComPtr для представления идентификатора указанного интерфейса.|  
|[Метод WeakRef::CopyTo](../windows/weakref-copyto-method.md)|Присваивает указатель на интерфейс \(при его наличии\) указанной переменной указателя.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор WeakRef::operator&](../Topic/WeakRef::operator&%20Operator.md)|Возвращает объект ComPtrRef, представляющий текущий объект WeakRef.|  
  
## Иерархия наследования  
 `ComPtr`  
  
 `WeakRef`  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)