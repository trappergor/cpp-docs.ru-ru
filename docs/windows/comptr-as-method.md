---
title: "Метод ComPtr::As | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As - метод"
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ComPtr::As
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает объект ComPtr, представляющий интерфейс, определенный указанным параметром шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Интерфейс для представления параметром `p`.  
  
 `p`  
 Объект ComPtr, представляющий интерфейс, заданный параметром `U`. Параметр `p` не должен ссылаться на текущий объект ComPtr.  
  
## <a name="remarks"></a>Примечания  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон — внутренний вспомогательный специализацию, которая поддерживает возможности языка C++, такие как [автоматически](../cpp/auto-cpp.md) ключевым словом вывода типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)