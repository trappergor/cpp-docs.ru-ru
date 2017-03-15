---
title: "Метод Module::GetActivationFactory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory - метод"
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Метод Module::GetActivationFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает фабрику активации для модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pActivatibleClassId`  
 Представляет IID класса среды выполнения.  
  
 `ppIFactory`  
 Представляет интерфейс IActivationFactory указанного класса среды выполнения.  
  
 `serverName`  
 Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в [ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md) макрос, или укажите `nullptr` для получения имени сервера по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
[Класс модуля](../windows/module-class.md)
 [макрос Activatableclass](../Topic/ActivatableClass%20Macros.md)