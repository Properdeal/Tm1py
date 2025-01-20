from TM1py.Services import TM1Service

# Configuration for TM1 Server (Localhost)
TM1_CONFIG = {
    "address": "localhost",   # Localhost address
    "port": 12354,            # Default TM1 REST API port (adjust if different)
    "user": "admin",          # TM1 username (replace if different)
    "password": "apple",      # TM1 password (replace with your password)
    "ssl": True               # Use True if SSL is enabled; False otherwise
}

# Establishing a Connection
try:
    with TM1Service(**TM1_CONFIG) as tm1:
        print("Connected to TM1 Server successfully!")
        # Additional actions can go here (e.g., retrieving server info)
        server_info = tm1.server.get_server_name()
        print(f"Server Name: {server_info}")
except Exception as e:
    print(f"Failed to connect to TM1 Server: {e}")
