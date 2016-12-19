---
title: "GetCodeForDllUnregisterServer | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllUnregisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllUnregisterServer - метод"
ms.assetid: 6b152943-8c30-49f4-a55c-d0cba8d27a17
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllUnregisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает соответствующий код для отмены регистрации сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      function GetCodeForDllUnregisterServer(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `nLineStart`  
 Номер строки (с нуля) начала функции.  
  
 `nLineEnd`  
 Отсчитываемый от нуля номер конца функции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая код для отмены регистрации сервера.  
  
## <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для получения соответствующего кода для отмены регистрации сервера:  
  
|Номер строки|Код|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|_AtlModule.UpdateRegistryAppId(false);|  
|2|HRESULT hRes = _AtlModule.UnregisterServer(TRUE);|  
|3|Если (hRes! = S_OK)|  
|4|\treturn hRes;|  
|5|IF (!) COleObjectFactory::UpdateRegistryAll(FALSE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS);|  
|7|Возвращает значение S_OK;|  
  
 Для каждой из строк, которые возвращаются `GetCodeForDllUnregisterServer` добавляет начальный символ табуляции (`\t`) и конечные пары символов «CR-LF» (возврат каретки и перевод строки) (`\r\n`).  
  
## <a name="example"></a>Пример  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllUnregisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.UnregisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>См. также  
 [Настройка мастеров с ++ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)