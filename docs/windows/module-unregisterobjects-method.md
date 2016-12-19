---
title: "Метод Module::UnregisterObjects | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::UnregisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterObjects - метод"
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::UnregisterObjects
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Параметры  
 `module`  
 Указатель на модуль.  
  
 `serverName`  
 Представляет имя, которое определяет подмножество объектов, затронутых этой операцией.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также раздел
 [Класс модулей](../windows/module-class.md)