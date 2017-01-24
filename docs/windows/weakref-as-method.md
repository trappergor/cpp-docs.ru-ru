---
title: "Метод WeakRef::As | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As - метод"
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: 6
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод WeakRef::As
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает определенный указатель ComPtr для представления указанного интерфейса.  
  
## Синтаксис  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### Параметры  
 `U`  
 Идентификатор интерфейса.  
  
 `ptr`  
 Когда эта операция завершается, объект, представляющий параметр `U`.  
  
## Возвращаемое значение  
  
-   Значение S\_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на причину неудачного завершения операции, а `ptr` устанавливается в значение `nullptr`.  
  
-   Значение S\_ОК, если операция завершилась успешно, но текущий объект WeakRef уже был выпущен. Параметр `ptr` устанавливается в значение `nullptr`.  
  
-   Значение S\_OK, если операция завершилась успешно, но текущий объект WeakRef не получен из параметра `U`. Параметр `ptr` устанавливается в значение `nullptr`.  
  
## Примечания  
 Если параметр `U` представляет собой IWeakReference или не получен из IInspectable, возникает ошибка.  
  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C\+\+, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md).  
  
 Начиная с пакета SDK для Windows 10 этот метод не устанавливает экземпляр WeakRef в значение `nullptr`, если не удалось получить слабую ссылку, поэтому следует избегать использования кода проверки ошибок, который проверяет наличие `nullptr` для WeakRef. Вместо этого проверьте возвращенное значение HRESULT, чтобы узнать, успешно ли выполнен метод, или проверьте `ptr` на наличие `nullptr`.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс WeakRef](../windows/weakref-class.md)