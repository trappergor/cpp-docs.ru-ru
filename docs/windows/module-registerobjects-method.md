---
title: "Метод Module::RegisterObjects | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterObjects - метод"
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Метод Module::RegisterObjects
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистрирует объекты модели COM или среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]), чтобы другие приложения могли к ним подключиться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Параметры  
 `module`  
 Массив объектов модели COM или среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]).  
  
 `serverName`  
 Имя сервера, который создал объекты.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
## <a name="see-also"></a>См. также раздел
[Класс модулей](../windows/module-class.md)