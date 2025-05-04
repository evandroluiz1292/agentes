from flask import Flask, request, jsonify
from flask_cors import CORS

app = Flask(__name__)
CORS(app)

@app.route("/webhook", methods=["POST"])
def webhook():
    data = request.json
    print("Mensagem recebida:", data)
    # lógica de resposta com IA Claude aqui
    return jsonify({"status": "recebido"})

if __name__ == "__main__":
    app.run(debug=True)
    
