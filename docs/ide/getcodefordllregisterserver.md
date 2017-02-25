---
title: "GetCodeForDllRegisterServer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllRegisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllRegisterServer - метод"
ms.assetid: 2fe733ad-3f1e-4020-9ce3-68956da7d41d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForDllRegisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получение надлежащего кода для регистрации сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      function GetCodeForDllRegisterServer(   
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
 Строка, содержащая код для регистрации сервера  
  
## <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для получения соответствующего кода для регистрации сервера:  
  
|Номер строки|Код|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|_AtlModule.UpdateRegistryAppId(true);|  
|2|HRESULT hRes = _AtlModule.RegisterServer(TRUE);|  
|3|Если (hRes! = S_OK)|  
|4|\treturn hRes;|  
|5|IF (!) COleObjectFactory::UpdateRegistryAll(TRUE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS);|  
|7|Возвращает значение S_OK;|  
  
 Для каждой из строк, которые возвращаются `GetCodeForDllRegisterServer` добавляет начальный символ табуляции (`\t`) и конечные пары символов «CR-LF» (возврат каретки и перевод строки) (`\r\n`).  
  
## <a name="example"></a>Пример  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllRegisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.RegisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>См. также  
 [Настройка мастеров с ++ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)