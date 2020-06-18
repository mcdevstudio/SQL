# SQL

# @@TRANCOUNT - use to count number of transactions 
# ROLLBACK - use for rollback every begin transaction (ignore scope)  
# COMMIT - use to commit transaction 
# **Both ROLLBACK and COMMIT**
# (need to have at least one transaction and be aware nested transaction that call rollback will cause error!)
# Example:
# begin 
#   begin try
#     begin tran
#       insert t1 vakues(2)
#       exec sp01
#       if(@@TRANCOUNT > 0)
#         commit
#     end try
#   begin catch
#       if(@@TRANCOUNT > 0)
#         rollback
#   end catch
# end
