# githubactions-test

f'DRIVER={{ODBC Driver 17 for SQL Server}};SERVER={server};DATABASE={database};UID={username};PWD={password}'

@app.get("/test_sql_connection") async def test_sql_connection(): try: # Establish a connection to the SQL Server with pyodbc.connect(connection_string) as conn: cursor = conn.cursor() # Execute a SELECT query cursor.execute("SELECT TOP 1 * FROM your_table") row = cursor.fetchone() # Fetch the result if row: return {"result": row} else: return {"result": "No data found"} except Exception as e: return {"error": str(e)}
