---
title: ConvertBSTRToString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- ConvertBSTRToString
dev_langs:
- C++
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 986fc35d1a84737b441d7259bba78459a42404e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Блок, относящийся только к системам Microsoft**  
  
 Преобразует `BSTR` значение **char \*** .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      char* __stdcall ConvertBSTRToString(  
   BSTR pSrc  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pSrc`  
 Переменная BSTR.  
  
## <a name="remarks"></a>Примечания  
 `ConvertBSTRToString` выделяет строку для удаления.  
  
## <a name="example"></a>Пример  
  
```  
// ConvertBSTRToString.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
  
int main() {  
   BSTR bstrText = ::SysAllocString(L"Test");  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);  
   printf_s("char * text: %s\n", lpszText2);  
  
   SysFreeString(bstrText);  
   delete[] lpszText2;  
}  
```  
  
```Output  
BSTR text: Test  
char * text: Test  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<comutil.h >.  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (в разделе [/Zc: wchar_t (wchar_t – это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) для получения дополнительной информации)  
  
## <a name="see-also"></a>См. также  
 [Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)