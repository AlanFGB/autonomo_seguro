import React, { useState, useEffect } from 'react';
import { 
  User, 
  Briefcase, 
  Users, 
  Home, 
  Calendar, 
  ShieldCheck, 
  TrendingUp, 
  Plus, 
  FileText,
  Clock,
  CheckCircle2,
  DollarSign
} from 'lucide-react';

const App = () => {
  const [activeTab, setActiveTab] = useState('dashboard');
  const [activities, setActivities] = useState([
    { id: 1, type: 'CLT Eventual', client: 'Empresa Alpha', date: '2023-10-25', description: 'Consultoria técnica pontual', value: 'R$ 500,00' },
    { id: 2, type: 'Familiar', client: 'Negócio de Família', date: '2023-10-24', description: 'Gestão de estoque', value: 'Sustento Familiar' },
    { id: 3, type: 'Parceria', client: 'Autônomo Silva', date: '2023-10-23', description: 'Apoio em projeto de design', value: 'R$ 300,00' },
  ]);

  const [showForm, setShowForm] = useState(false);
  const [newActivity, setNewActivity] = useState({
    type: 'Independente',
    client: '',
    description: '',
    date: new Date().toISOString().split('T')[0]
  });

  const handleAddActivity = (e) => {
    e.preventDefault();
    const activity = {
      ...newActivity,
      id: Date.now(),
      value: newActivity.type === 'Familiar' ? 'Sustento' : 'R$ 0,00'
    };
    setActivities([activity, ...activities]);
    setShowForm(false);
    setNewActivity({ type: 'Independente', client: '', description: '', date: new Date().toISOString().split('T')[0] });
  };

  return (
    <div className="min-h-screen bg-slate-50 text-slate-900 font-sans">
      {/* Header */}
      <header className="bg-indigo-700 text-white p-6 shadow-lg">
        <div className="max-w-4xl mx-auto flex justify-between items-center">
          <div>
            <h1 className="text-2xl font-bold flex items-center gap-2">
              <ShieldCheck className="w-8 h-8 text-emerald-400" />
              Autônomo Seguro
            </h1>
            <p className="text-indigo-100 text-sm italic">O Manifesto da Independência e Sustento</p>
          </div>
          <div className="hidden md:block text-right">
            <span className="block text-xs uppercase tracking-widest opacity-75">Status</span>
            <span className="font-semibold text-emerald-400">Independente Ativo</span>
          </div>
        </div>
      </header>

      <main className="max-w-4xl mx-auto p-4 md:p-8">
        {/* Navigation Tabs */}
        <nav className="flex gap-4 mb-8 overflow-x-auto pb-2 border-b border-slate-200">
          <button 
            onClick={() => setActiveTab('dashboard')}
            className={`flex items-center gap-2 px-4 py-2 rounded-lg transition-colors whitespace-nowrap ${activeTab === 'dashboard' ? 'bg-indigo-100 text-indigo-700 font-bold' : 'hover:bg-slate-200'}`}
          >
            <TrendingUp size={18} /> Dashboard
          </button>
          <button 
            onClick={() => setActiveTab('logs')}
            className={`flex items-center gap-2 px-4 py-2 rounded-lg transition-colors whitespace-nowrap ${activeTab === 'logs' ? 'bg-indigo-100 text-indigo-700 font-bold' : 'hover:bg-slate-200'}`}
          >
            <FileText size={18} /> Registros de Autonomia
          </button>
          <button 
            onClick={() => setActiveTab('info')}
            className={`flex items-center gap-2 px-4 py-2 rounded-lg transition-colors whitespace-nowrap ${activeTab === 'info' ? 'bg-indigo-100 text-indigo-700 font-bold' : 'hover:bg-slate-200'}`}
          >
            <ShieldCheck size={18} /> Conceitos
          </button>
        </nav>

        {activeTab === 'dashboard' && (
          <div className="space-y-6 animate-in fade-in duration-500">
            {/* Stats Grid */}
            <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
              <div className="bg-white p-6 rounded-2xl shadow-sm border border-slate-100 flex items-center gap-4">
                <div className="p-3 bg-emerald-100 text-emerald-600 rounded-full">
                  <Briefcase size={24} />
                </div>
                <div>
                  <p className="text-xs text-slate-500 uppercase">Projetos CLT (Mês)</p>
                  <p className="text-xl font-bold">2 Eventos</p>
                </div>
              </div>
              <div className="bg-white p-6 rounded-2xl shadow-sm border border-slate-100 flex items-center gap-4">
                <div className="p-3 bg-amber-100 text-amber-600 rounded-full">
                  <Home size={24} />
                </div>
                <div>
                  <p className="text-xs text-slate-500 uppercase">Apoio Familiar</p>
                  <p className="text-xl font-bold">Ativo</p>
                </div>
              </div>
              <div className="bg-white p-6 rounded-2xl shadow-sm border border-slate-100 flex items-center gap-4">
                <div className="p-3 bg-indigo-100 text-indigo-600 rounded-full">
                  <Users size={24} />
                </div>
                <div>
                  <p className="text-xs text-slate-500 uppercase">Parcerias</p>
                  <p className="text-xl font-bold">4 Colegas</p>
                </div>
              </div>
            </div>

            {/* Quick Action */}
            <div className="bg-gradient-to-r from-indigo-600 to-indigo-800 rounded-2xl p-6 text-white flex flex-col md:flex-row justify-between items-center gap-4 shadow-md">
              <div>
                <h2 className="text-xl font-bold mb-1">Registrar Atividade de Valor</h2>
                <p className="text-indigo-100 text-sm">Documente sua entrega social para garantir sua prova de autonomia.</p>
              </div>
              <button 
                onClick={() => {setActiveTab('logs'); setShowForm(true);}}
                className="bg-white text-indigo-700 px-6 py-2 rounded-full font-bold hover:bg-indigo-50 transition-all flex items-center gap-2 shadow-sm"
              >
                <Plus size={20} /> Novo Registro
              </button>
            </div>

            {/* Recent Activity */}
            <div className="bg-white rounded-2xl shadow-sm border border-slate-100 overflow-hidden">
              <div className="p-4 border-b border-slate-50 bg-slate-50 flex justify-between items-center">
                <h3 className="font-bold text-slate-700">Fluxo Recente</h3>
              </div>
              <div className="divide-y divide-slate-100">
                {activities.slice(0, 3).map((act) => (
                  <div key={act.id} className="p-4 flex justify-between items-center hover:bg-slate-50 transition-colors">
                    <div className="flex gap-4 items-center">
                      <div className={`w-2 h-10 rounded-full ${act.type === 'Familiar' ? 'bg-amber-400' : act.type === 'CLT Eventual' ? 'bg-red-400' : 'bg-emerald-400'}`}></div>
                      <div>
                        <p className="font-semibold text-slate-800">{act.description}</p>
                        <p className="text-xs text-slate-500 flex items-center gap-1">
                          <User size={12} /> {act.client} • <Calendar size={12} /> {act.date}
                        </p>
                      </div>
                    </div>
                    <div className="text-right">
                      <span className="text-sm font-medium text-slate-600 bg-slate-100 px-2 py-1 rounded">{act.type}</span>
                    </div>
                  </div>
                ))}
              </div>
            </div>
          </div>
        )}

        {activeTab === 'logs' && (
          <div className="space-y-6 animate-in slide-in-from-bottom-4 duration-500">
            {showForm ? (
              <div className="bg-white p-6 rounded-2xl shadow-md border-t-4 border-indigo-500">
                <h3 className="text-xl font-bold mb-4 flex items-center gap-2">
                  <Plus className="text-indigo-500" /> Nova Prova de Autonomia
                </h3>
                <form onSubmit={handleAddActivity} className="space-y-4">
                  <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                      <label className="block text-xs font-bold text-slate-500 uppercase mb-1">Tipo de Trabalho</label>
                      <select 
                        className="w-full p-3 bg-slate-50 border border-slate-200 rounded-xl outline-none focus:ring-2 focus:ring-indigo-400 transition-all"
                        value={newActivity.type}
                        onChange={(e) => setNewActivity({...newActivity, type: e.target.value})}
                      >
                        <option value="Independente">Independente Solo</option>
                        <option value="CLT Eventual">CLT Eventual (Poucas vezes/mês)</option>
                        <option value="Parceria">Parceria com Autônomo</option>
                        <option value="Familiar">Trabalho Familiar / Sustento</option>
                      </select>
                    </div>
                    <div>
                      <label className="block text-xs font-bold text-slate-500 uppercase mb-1">Tomador / Cliente / Parceiro</label>
                      <input 
                        required
                        className="w-full p-3 bg-slate-50 border border-slate-200 rounded-xl outline-none focus:ring-2 focus:ring-indigo-400 transition-all"
                        placeholder="Ex: Farmácia Brito ou Nome do Familiar"
                        value={newActivity.client}
                        onChange={(e) => setNewActivity({...newActivity, client: e.target.value})}
                      />
                    </div>
                  </div>
                  <div>
                    <label className="block text-xs font-bold text-slate-500 uppercase mb-1">Descrição do Valor Gerado</label>
                    <textarea 
                      required
                      className="w-full p-3 bg-slate-50 border border-slate-200 rounded-xl outline-none focus:ring-2 focus:ring-indigo-400 transition-all"
                      placeholder="Descreva como seu trabalho beneficiou a sociedade ou o núcleo familiar hoje..."
                      rows="3"
                      value={newActivity.description}
                      onChange={(e) => setNewActivity({...newActivity, description: e.target.value})}
                    ></textarea>
                  </div>
                  <div className="flex gap-2 justify-end pt-2">
                    <button 
                      type="button"
                      onClick={() => setShowForm(false)}
                      className="px-6 py-2 rounded-xl border border-slate-200 text-slate-600 hover:bg-slate-50 transition-all font-semibold"
                    >
                      Cancelar
                    </button>
                    <button 
                      type="submit"
                      className="px-6 py-2 rounded-xl bg-indigo-600 text-white hover:bg-indigo-700 transition-all font-bold shadow-sm"
                    >
                      Salvar Registro
                    </button>
                  </div>
                </form>
              </div>
            ) : (
              <div className="bg-white rounded-2xl shadow-sm border border-slate-100 overflow-hidden">
                <div className="p-6 border-b border-slate-50 flex justify-between items-center bg-slate-50/50">
                  <h3 className="font-bold text-slate-700">Histórico de Autonomia</h3>
                  <button onClick={() => setShowForm(true)} className="text-indigo-600 text-sm font-bold flex items-center gap-1 hover:underline">
                    <Plus size={16} /> Adicionar
                  </button>
                </div>
                <div className="divide-y divide-slate-100">
                  {activities.map((act) => (
                    <div key={act.id} className="p-6 hover:bg-slate-50 transition-all group">
                      <div className="flex flex-col md:flex-row md:items-center justify-between gap-4">
                        <div className="flex gap-4">
                          <div className={`mt-1 w-10 h-10 rounded-xl flex items-center justify-center shrink-0 ${
                            act.type === 'Familiar' ? 'bg-amber-100 text-amber-600' : 
                            act.type === 'CLT Eventual' ? 'bg-red-100 text-red-600' : 
                            'bg-emerald-100 text-emerald-600'
                          }`}>
                            {act.type === 'Familiar' ? <Home size={20}/> : act.type === 'CLT Eventual' ? <Briefcase size={20}/> : <User size={20}/>}
                          </div>
                          <div>
                            <span className="inline-block text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded bg-slate-200 text-slate-600 mb-1">
                              {act.type}
                            </span>
                            <h4 className="font-bold text-slate-800 text-lg leading-tight">{act.description}</h4>
                            <div className="flex flex-wrap gap-x-4 gap-y-1 mt-2 text-sm text-slate-500">
                              <span className="flex items-center gap-1"><User size={14} className="opacity-70"/> {act.client}</span>
                              <span className="flex items-center gap-1"><Calendar size={14} className="opacity-70"/> {act.date}</span>
                              <span className="flex items-center gap-1 text-emerald-600 font-medium"><DollarSign size={14}/> {act.value}</span>
                            </div>
                          </div>
                        </div>
                        <div className="flex items-center gap-2 self-end md:self-center opacity-0 group-hover:opacity-100 transition-opacity">
                           <CheckCircle2 className="text-emerald-500" size={24} />
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            )}
          </div>
        )}

        {activeTab === 'info' && (
          <div className="space-y-6 animate-in fade-in duration-500">
            <div className="bg-white p-8 rounded-2xl shadow-sm border border-slate-100">
              <h3 className="text-2xl font-bold mb-6 text-indigo-700">Diferenciação do Trabalho Independente</h3>
              
              <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div className="bg-slate-50 p-5 rounded-xl border-l-4 border-blue-500">
                  <h4 className="font-bold text-blue-700 flex items-center gap-2 mb-2">
                    <TrendingUp size={18}/> CLT (Evolução)
                  </h4>
                  <p className="text-sm text-slate-600 leading-relaxed">
                    Focado na carreira vertical. Promoções, aumentos anuais e estabilidade dentro de uma hierarquia. Subordinação em troca de garantias.
                  </p>
                </div>

                <div className="bg-slate-50 p-5 rounded-xl border-l-4 border-amber-500">
                  <h4 className="font-bold text-amber-700 flex items-center gap-2 mb-2">
                    <Clock size={18}/> Judicial (Manutenção)
                  </h4>
                  <p className="text-sm text-slate-600 leading-relaxed">
                    Focado na disputa de direitos. Busca manter ou recuperar o que foi sonegado, tentando transformar relações de fato em direitos trabalhistas.
                  </p>
                </div>
              </div>

              <div className="mt-8 bg-indigo-50 p-6 rounded-2xl border border-indigo-100 relative overflow-hidden">
                <div className="relative z-10">
                  <h4 className="font-bold text-indigo-800 text-lg mb-4 flex items-center gap-2">
                    <CheckCircle2 className="text-indigo-600"/> O Independente (Sustento e Valor)
                  </h4>
                  <ul className="space-y-3 text-slate-700">
                    <li className="flex gap-3 text-sm">
                      <span className="font-bold text-indigo-600">•</span>
                      <span><strong>Trabalho Solo ou Familiar:</strong> Focado na renda direta e no bem-estar do núcleo familiar.</span>
                    </li>
                    <li className="flex gap-3 text-sm">
                      <span className="font-bold text-indigo-600">•</span>
                      <span><strong>Colaboração Plural:</strong> Pode atender CLT pontualmente (eventualidade) ou outros autônomos.</span>
                    </li>
                    <li className="flex gap-3 text-sm">
                      <span className="font-bold text-indigo-600">•</span>
                      <span><strong>Benefício Social:</strong> O trabalho gera valor imediato e renda que circula na comunidade.</span>
                    </li>
                  </ul>
                </div>
                <div className="absolute -right-8 -bottom-8 text-indigo-200/30 rotate-12">
                   <ShieldCheck size={160} />
                </div>
              </div>
            </div>
          </div>
        )}
      </main>

      {/* Footer Info */}
      <footer className="max-w-4xl mx-auto p-8 text-center text-slate-400 text-xs">
        <p>Este sistema é uma ferramenta de apoio para documentação de autonomia.</p>
        <p className="mt-2">Independência • Autonomia • Sustento Familiar • Sociedade</p>
      </footer>
    </div>
  );
};

export default App;
