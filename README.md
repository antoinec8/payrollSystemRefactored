# payrollSystemRefactored

Sistema de folha de pagamento refatorado. 
\
REFACTORING
\
\
\
STRATEGY
\
Foi aplicado o DP Strategy na classe PaymentSchedule para solucionar problemas de complexidade dos métodos de pagamento para os diferentes tipos de agenda: Cada agenda agora possui uma classe própria, onde implementam os métodos getMonthlyDiv e isDateToPay, definidos na interface ScheduleStrategy; 

MEMENTO
\
Foi aplicado o DP Memento para prover as funcionalidades de undo/redo da Classe Company: Os métodos de salvar estado atual, undo e redo são de responsabilidade da classe CaretakerCompany, enquanto o estado é salvo como um objeto da classe Memento Company;

REMOVAL OF GENERATIVE SPECULATION
\
Remoção dos métodos, parâmetros e importações não utilizados no projeto;

HIDE DELEGATED
\
Criação dos métodos isCommissioned, isSalaried e isHourly para ocultar a chamada dos métodos .getClass().isAssignableFrom(). 
\
\
\
CODE SMELLS
\
\
Código duplicado nos métodos editEmployeeMenu e createEmployee da classe EmployeeController;
\
Métodos construtores da classe Employee;
\
Classes TimeCard eAdditionalServiceTax, além de, addSaleResult e addTimeCard são muito similares;
\
Muitos métodos não são utilizados, como métodos get/set e construtores vazios e isLastWeekOfMonth da classe DateUtil;
\
Parâmetro id da classe PaymentSchedule não é utilizado;
\
Importações de classes não utilizadas nas classes Company e EmployeeSyndicate;
\
No método editEmployeeMenu da classe EmployeeController, a chamada dos métodos construtores das classes Hourly, Commissioned e Salaried recebem parâmetros de um único objeto ao invés do mesmo;
\
Método menu da classe Menu possui diversos tratamentos para as opções do menu;
\
Classe Menu possui métodos da lógica das funcionalidades de undo/redo;
\
Classe PaymentController trata tanto das PaymentSchedule quanto da payroll.
