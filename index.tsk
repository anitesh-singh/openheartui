import { useState } from "react";

export default function Home() {
  const [log, setLog] = useState("");
  const [logs, setLogs] = useState<string[]>([]);

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    if (log.trim()) {
      setLogs([log, ...logs]);
      setLog("");
    }
  };

  return (
    <main className="min-h-screen bg-white p-6 text-gray-800">
      <div className="max-w-xl mx-auto">
        <h1 className="text-3xl font-bold mb-6">🌍 Global Heart Sync</h1>

        {/* Practice Log Form */}
        <form onSubmit={handleSubmit} className="mb-6">
          <label className="block mb-2 font-semibold">Log Your Practice</label>
          <textarea
            className="w-full border p-3 rounded-lg mb-2"
            rows={4}
            value={log}
            onChange={(e) => setLog(e.target.value)}
            placeholder="Describe your practice session..."
          />
          <button
            type="submit"
            className="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700"
          >
            Submit
          </button>
        </form>

        {/* Practice Log History */}
        {logs.length > 0 && (
          <div className="mb-6">
            <h2 className="text-xl font-semibold mb-2">Your Logs</h2>
            <ul className="space-y-2">
              {logs.map((entry, i) => (
                <li key={i} className="p-3 bg-gray-100 rounded">
                  {entry}
                </li>
              ))}
            </ul>
          </div>
        )}

        {/* Badge Display */}
        <div className="mt-8">
          <h2 className="text-xl font-semibold mb-2">🏅 Your Badges</h2>
          <div className="flex gap-4">
            <div className="bg-yellow-200 text-yellow-800 px-4 py-2 rounded-full shadow">
              First Log
            </div>
            {logs.length >= 3 && (
              <div className="bg-green-200 text-green-800 px-4 py-2 rounded-full shadow">
                3 Logs Badge
              </div>
            )}
          </div>
        </div>
      </div>
    </main>
  );
}