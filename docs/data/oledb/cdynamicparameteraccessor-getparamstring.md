---
title: CDynamicParameterAccessor::GetParamString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
dev_langs:
- C++
helpviewer_keywords:
- GetParamString method
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b8dadcb70dd29f1a70aea288eb0f63b22591561e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicparameteraccessorgetparamstring"></a>CDynamicParameterAccessor::GetParamString
Получает строковые данные указанного параметра, сохраненного в буфере.  
  
## <a name="syntax"></a>Синтаксис  
  
```
bool GetParamString(DBORDINAL nParam,  
  CSimpleStringA& strOutput) throw();bool GetParamString(DBORDINAL nParam,  
  CSimpleStringW& strOutput) throw();bool GetParamString(DBORDINAL nParam,  
  CHAR* pBuffer,  
   size_t* pMaxLen) throw();bool GetParamString(DBORDINAL nParam,  
  WCHAR* pBuffer,  
   size_t* pMaxLen) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nParam`  
 [in] Номер параметра (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером — это индекс параметра, в зависимости от порядка в SQL или хранимой процедуры. В разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) в качестве примера.  
  
 `strOutput`  
 [out] ANSI (**CSimpleStringA**) или Юникод (**CSimpleStringW**) строковые данные указанного параметра. Необходимо передать параметр типа `CString`, например:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 [out] Указатель на ANSI (**CHAR**) или Юникод (**WCHAR**) строковые данные указанного параметра.  
  
 `pMaxLen`  
 [out] Указатель на размер буфера, на который указывает `pBuffer` (в символах, включая завершающий нуль-символ).  
  
## <a name="remarks"></a>Примечания  
 Возвращает **true** в случае успешного выполнения или **false** при сбое.  
  
 Если `pBuffer` имеет значение NULL, этот метод будет задать необходимый размер буфера в памяти, на который указывает `pMaxLen` и возвращают **true** без копирования данных.  
  
 Этот метод завершится ошибкой, если буфер `pBuffer` недостаточно велик для хранения вся строка.  
  
 Используйте `GetParamString` для получения параметров строковые данные из буфера. Используйте [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) для получения нестроковые данные параметров из буфера.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)