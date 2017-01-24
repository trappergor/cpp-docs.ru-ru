---
title: "Метод Module::GetClassObject | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetClassObject - метод"
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::GetClassObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает кэш фабрик классов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `clsid`  
 Идентификатор класса.  
  
 `riid`  
 Запрошенный идентификатор интерфейса.  
  
 `ppv`  
 Указатель на возвращаемый объект.  
  
 `serverName`  
 Имя сервера, указанное в макросе `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` или `ActivatableClass`; в противном случае — значение `nullptr` для получения имени сервера по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="remarks"></a>Примечания  
 Используйте этот метод только для модели COM, а не для среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]). Этот метод реализует только методы IClassFactory.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)