Estado
======

using System; using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.Mvc; using LadoAnimal.Models;  namespace LadoAnimal.Controllers {     public class EstadoController : Controller     {         //         // GET: /Estado/          public ActionResult Index()         {            var estado = Estado.FindAll();            return View (estado);         }          public ActionResult Create ()         {             var estado = new Estado();             return View(estado);         }                            [HttpPost]         public ActionResult Create(Estado estado)         {             Estado.Create(estado);             return RedirectToAction("Index");         }                   public ActionResult Delete(int id)         {             Estado estado = Estado.Find(id);             estado.Delete();             return RedirectToAction("Index");         }                      public ActionResult Details(int id)         {             Estado estado = Estado.Find(id);             return View(estado);         }               public ActionResult Edit(int id)             {                 Estado estado = Estado.Find(id);                  return View(estado);             }          }                 }