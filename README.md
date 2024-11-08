# DIO_Assistente_Delivery
### Criando um Assistente de Delivery com AWS Step Functions e Bedrock
#### Feito usando AI
#### JSON

{
  
  "StartAt": "GetOrder",
  
  "States": {
    
	"GetOrder": {
      
	  "Type": "Task",
      
	  "Resource": "arn:aws:lambda:us-east-1:123456789012:function:GetOrderFunction",
      
	  "Next": "CheckAvailability"
    
	},
    
	"CheckAvailability": {
      
	  "Type": "Task",
      
	  "Resource": "arn:aws:lambda:us-east-1:123456789012:function:CheckAvailabilityFunction",
      
	  "Next": "CalculatePrice"
    
	},
    
	// ... outros estados para calcular preço, confirmar pedido, etc.
    
	"Failure": {
      
	  "Type": "Fail"
    
	}
  
  }

}
